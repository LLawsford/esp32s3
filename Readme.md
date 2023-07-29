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


espup will create an export file that contains some environment variables required to build projects.
On Unix based systems ($HOME/export-esp.sh). There are different ways of sourcing the file:

- Source this file in every terminal:
Source the export file: . $HOME/export-esp.sh
This approach requires running the command in every new shell.

- Create an alias for executing the export-esp.sh:
Copy and paste the following command to your shell’s profile (.profile, .bashrc, .zprofile, etc.): alias get_esprs='. $HOME/export-esp.sh'
Refresh the configuration by restarting the terminal session or by running source [path to profile], for example, source ~/.bashrc.
This approach requires running the alias in every new shell.

- Add the environment variables to your shell's profile directly:
Add the content of $HOME/export-esp.sh to your shell ’s profile: cat $HOME/export-esp.sh >> [path to profile], for example, cat $HOME/export-esp.sh >> ~/.bashrc.
Refresh the configuration by restarting the terminal session or by running source [path to profile], for example, source ~/.bashrc.
This approach does not require any sourcing. The export-esp.sh script will be sourced automatically in every shell.


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

