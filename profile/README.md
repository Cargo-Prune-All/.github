<p align="center">
  <img src="https://github.com/Cargo-Prune-All/.github/assets/72998897/9ef22e0d-a24e-419f-a406-2e892aa8a396" alt="drawing" width="200"/>
</p>

# <p align="center">Cargo-Prune-All</p>

## What is it?
Cargo prune all is a cli tool to delete common build folders on your computer to save storage. It supports commands to remove known folders like "node_modules" for node, "target" for rust and so on. It also supports the functionallity to add custom types and procedures for your liking.

## Installation
### Cargo
#### Linux
On linux you simply have to run the following command to install cargo:
```
curl https://sh.rustup.rs -sSf | sh
```

#### Windows
For windows you have to visit the [rust installation page](https://www.rust-lang.org/learn/get-started) and install the installer fitting your operating system. After running the script you have cargo installed on your system.

### Cargo-Prune-All
To install the tool onto your system run the following command:
```
cargo install cargo-prune-all
```
You can now use the cli tool.

## Usage
### Input for pruning
The tool takes in some required and optional arguments:
```
cargo prune-all <profile> --location <path> --recursive --min-age <min-age> --min-size <min-size> --interactive 
```
|             | required           | type   | description                                                       | example               | shorthand |
|-------------|--------------------|--------|-------------------------------------------------------------------|-----------------------|-----------|
| profile     | :white_check_mark: | text   | The profile describing the folders to delete                      | node                  | /         |
| location    | :x:                | path   | The path to the folder to search in                               | C://path/to/directory | -l        |
| recursive   | :x:                | /      | If you want to search recursively inside the location             | /                     | -r        |
| min-age     | :x:                | number | The minimum amount of days the directory has to be to get deleted | 5                     | -a        |
| min-size    | :x:                | number | The minimum size of the folder to get deleted in MB               | 500                   | -s        |
| interactive | :x:                | /      | If you want to confirm the deletion of the folders                | /                     | -i        |

### Input for creating a profile
The creation of a new profile is pretty simple:
```
cargo prune-all --create <name> --matches <name...>
```
|         | required           | type         | description                        | example             | shorthand |
|---------|--------------------|--------------|------------------------------------|---------------------|-----------|
| create  | :white_check_mark: | text         | The name of the profile            | node_and_rust       | -c        |
| matches | :white_check_mark: | List of text | The names of directories to delete | node_modules target | -m        |

### Input for deleting a profile
It's also no big deal to delete a profile
```
cargo prune-all --delete node_and_rust
```
|        | required           | type | description                       | example       | shorthand |
|--------|--------------------|------|-----------------------------------|---------------|-----------|
| delete | :white_check_mark: | /    | The name of the profile to delete | node_and_rust | -d        |

