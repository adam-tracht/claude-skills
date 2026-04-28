# Claude Skills

Personal Claude Code skills.

## Skills

### deslop
Removes AI writing patterns from prose. Invoke with `/deslop` or paste the condensed prompt into any AI chat. Covers AI vocabulary, copula avoidance, formulaic structures, formatting tells, filler, and more. Includes a full pattern catalog in `references/patterns.md`.

### caveman
Ultra-compressed communication mode. Cuts all filler and responds in minimal, direct language.

### council
Multi-perspective deliberation using parallel subagents. Each councilor (Skeptic, Advocate, Pragmatist, First-Principles, Minimalist) responds independently, a neutral panel evaluates, and a Chairman synthesizes. Good for decisions where you want genuine push-back before committing.

 ## Installation                                   
                                                                                                                                                                                               
  ### Claude Code
                                                                                                                                                                                               
  Each skill in this repo is a complete plugin (`<name>/.claude-plugin/plugin.json` + `<name>/skills/<name>/SKILL.md`). To install:                                                            
   
  1. Copy the skill folder into the local plugin cache:                                                                                                                                        
     ```bash                                        
     cp -R <skill-name> ~/.claude/plugins/cache/local/                                                                                                                                         
     ```                                                                                                                                                                                       
   
  2. Add an entry to `~/.claude/plugins/installed_plugins.json` under the top-level `plugins` object:                                                                                          
     ```json                                        
     "<skill-name>@local": [{                                                                                                                                                                  
       "scope": "user",                                                                                                                                                                        
       "installPath": "/Users/<you>/.claude/plugins/cache/local/<skill-name>",
       "version": "1.0.0",                                                                                                                                                                     
       "installedAt": "2026-01-01T00:00:00.000Z",   
       "lastUpdated": "2026-01-01T00:00:00.000Z"                                                                                                                                               
     }]                                             
     ```                                                                                                                                                                                       
                                                                                                                                                                                               
  3. Enable it in `~/.claude/settings.json`:
     ```json                                                                                                                                                                                   
     "enabledPlugins": {                            
       "<skill-name>@local": true
     }
     ```                                                                                                                                                                                       
   
  Both registration files are required or the skill won't appear. Restart Claude Code to pick up the changes.                                                                                  
                                                    
  Optional — add a slash command at `~/.claude/commands/<skill-name>.md`:                                                                                                                      
  ```                                               
  Invoke the `<skill-name>:<skill-name>` skill now. $ARGUMENTS                                                                                                                                 
  ```                                                                                                                                                                                          
   
  ### Claude chat (claude.ai)                                                                                                                                                                  
                                                    
  Chat uses zip upload, not filesystem. The zip must have the skill folder at the **root** (one level deep), not nested under `skills/`.                                                       
   
  ```bash                                                                                                                                                                                      
  cd <skill-name>/skills && zip -r ~/Desktop/<skill-name>.zip <skill-name>/
  ```                                                                                                                                                                                          
                                                    
  The archive should look like:                                                                                                                                                                
  ```
  <skill-name>/                                                                                                                                                                                
  ├── SKILL.md                                      
  └── references/   # if present
  ```

  Then in claude.ai: **Settings > Customize > Skills > Upload**.                                                                                                                               
   
  Two notes on what I changed:                                                                                                                                                                 
  - I'd add the JSON blocks because the silent-fail mode (skill simply doesn't appear) is the worst kind of error to debug from a one-line instruction.
  - Worth being explicit that the chat zip layout differs from the Claude Code layout — that nesting error is annoying to hit and the message isn't obvious until you've seen it once.
