
# Git-Adventure
first steps with github, git and md-Syntax ... and more to come

[git help](/git-help.md)
# WBS Coding School
Lets learn something new everyday

### Lets try UML in md-Syntax
You can render diagrams using [Mermaid](https://mermaidjs.github.io/). 

Sequence diagram of "bad git"-use, depending on teamsize and project:
```mermaid
sequenceDiagram   
    rect rgb(191, 223, 255)   
        main->>dev: git pull origin main
            rect rgb(200, 150, 255)
                dev->>dev: Works
            end
		dev->>main: git push origin main
		Note  right of  dev:  better not push directly into main
    end


```
