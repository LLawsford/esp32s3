This repo is created by mixing couple resources for ESP32S3 board.

# Things to adjust: 
## 1. Cargo.toml
[build]
target = "<your_target>"

[target.<your_target>]

# Installation
espup:
```bash cargo install espup```
```bash espup install```

ldproxy:
```bash cargo install ldproxy```

# Using containers
there is docker image https://hub.docker.com/r/espressif/idf-rust/tags

it can be used to develop and build app, and then program can be flashed from your main machine onto the board
there is also option to flash board through web (https://github.com/esp-rs/esp-web-flash-server)

# Generating project
there are some common templates, one of which is esp-idf-template (contains std rust package)
(esp-template has no std)
```bash cargo generate esp-rs/esp-idf-template cargo```

# Build & run 
```bash cargo build && cargo run```
it uses espflash under the hood to flash and monitor the board

# Config
there is this little package called toml-cfg that uses cfg.toml, watch out for proper section naming there (it should match project name)

