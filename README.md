
# Git-Adventure
first steps with github, git and md-Syntax ... and more to come

# WBS Coding School
Lets learn something new everyday

### Lets try UML in md-Syntax
You can render diagrams using [Mermaid](https://mermaidjs.github.io/). 
For example, this will produce a sequence diagram:
```mermaid
sequenceDiagram
    participant main
    participant dev    
    rect rgb(191, 223, 255)   
        main->>dev: git pull origin main
            rect rgb(200, 150, 255)
                dev->>dev: Works
            end
		dev->>main: git push origin main
    end
