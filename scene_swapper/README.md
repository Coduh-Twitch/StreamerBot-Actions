# Scene Swapping
Commands to maintain a list of scenes with a key, which can be swapped between at any time.

## Import Includes
- **Command**: `!screen` - Swap the current scene
- **Command**: `!addscreen` - Add a key+screen combo to the global variables
- **Action**: `screen` - Triggered by the `!screen` command, runs custom C# code.
- **Action**: `addscreen` - Triggered by the `!addscreen` command, runs custom C# code.

## Configuration Required
> 1. Initialize the variable by creating a **global variable** called `screen` with the following format. **Include at least 2 scene+key combos in the initial variable**
> - `key,Scene Name|key2,Scene Name 2`
> - **Example**: `gaming,Fullscreen Game|webcam,Camera Only`
> 2. In the C# code editor's `References` tab, right click to add all of the required references noted at the bottom of this README. **Do this for all actions included in the import**

## Commands
### Swap Scenes
Using a predefined key, swap to the associated scene in OBS
> `!screen {key}`
> 
> **Example Usages**:
> - `!screen gaming`
> - `!screen webcam`

### Add Scene
Add a scene + key combo to the global `scenes` variable
> `!addscreen {key} {scene name}`
> 
> **Example Usages**:
> - `!addscreen gaming Fullscreen Game`
> - `!addscreen webcam Camera Only`


---

### Required References (`addscreen` action)
- mscorlib.dll (.NET)
- System.dll (.NET)
- System.Core.dll (.NET)
- System.Text.Json.dll (.NET)

### Required References (`screen` action)
- mscorlib.dll (.NET)
- System.Core.dll (.NET)
