# Handy `[alias]` to have in the git config file  

edit with Bash command: `git config -e --global`

## logs

`l = log --graph --oneline --decorate`

`ll = log --graph --oneline --decorate --branches --tags `

`lll = log --graph --simplify-by-decoration --pretty=format:'%d' --all `

## templating 

`clonetemplatets = clone https://github.com/maldestor95/nodejs_typescript_template.git -o template --depth 1 --no-tags `
	
`newts = "!f(){ git clonetemplatets "$1" && cd ./"$1" && git remote remove template ; };f" `
