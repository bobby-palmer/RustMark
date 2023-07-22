# quickclip
A directory book marker written in rust 🦀!  
## Installation
with cargo run : `cargo install quickclip`  
then add your respective shells startup script:
<details closed>
  <summary>fish</summary>
  <br>
  add `quickclip init fish | source` to your config file.  
  this is usually in fish.config  
</details>
<details closed>
  <summary>zsh</summary>
  <br>
  add `eval "$(quickclip init zsh)"` to your config file.  
  this is usually in .zshrc  
</details>
<details closed>
  <summary>bash</summary>
  <br>
  add `eval "$(quickclip init bash)"` to your config file.  
  this is usually in .bashrc  
</details>  

## Usage
- add new mark with `quickclip {NAME}`
  - if NAME is not specified, it will default to the folder name.  
- list all marks with `quickclip list`  
- remove a clip with ` quickclip remove {NAME}`
- print a clip path with `quickclip goto {NAME}`
- open a GUI for the goto command with `quickclip goto`
### Tips
- Saving quickclip as an alias for your shell such as `alias qc = quickclip`
- create a shell goto function to cd to the output of the quickclip goto command
ie (in fish) :
```
# set to cd using bookmarks
function goto
  set -l path (command quickclip goto $argv)
  cd -- "$path"
end

```
## Roadmap
Eventually I would like to add a fuzzy finder to the tui for selecting the book mark. 
Currently, though I am more focused on polishing up the current features such as:
- Better error handling
- confirming before overwriting a book mark
- auto creation of the goto shell function
