## hyprparser

A parser for hyprland written in rust 🚀🦀

---

### Examples

```rust
fn main() {
    let home = std::env::var("HOME").unwrap();
    let config_path = PathBuf::from(home).join(".config/hypr/hyprland.conf");

    let config_str = fs::read_to_string(&config_path).unwrap();

    let mut parsed_config = parse_config(&config_str);

    parsed_config.add_entry("decoration", "rounding = 10");
    parsed_config.add_entry("decoration.blur", "enabled = true");
    parsed_config.add_entry("decoration.blur", "size = 10");
    parsed_config.add_empty_line();

    let updated_config_str = parsed_config.to_string();

    fs::write(&config_path, updated_config_str).unwrap();

    println!("Updated hyprland.conf with new configurations.");
}
```

### Credits

- [Nyx](https://github.com/nnyyxxxx) - For making the parser
- [Vaxry](https://github.com/vaxerski) - For Hyprland
- [Hyprland](https://github.com/hyprwm/Hyprland) - The window manager