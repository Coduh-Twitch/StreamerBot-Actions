# Source Transform Commands
These commands were designed with the intention of moving a webcam source around on a shared nested scene, enabling full control over a single source's **position** via chat commands.

## Import Includes
- **Command**: `!camera` - Control the chosen source
- **Action**: `move camera` - Triggered by the `!camera` command, runs custom C# code.

## Configuration Required
> 1. Open the C# code editor and replace the following values near the top of the file:
> - camSceneName: ~~Webcam~~ -> The name of your nested scene  
> - camSourceName: ~~Image~~ -> The name of the source you wish to manage
> - filterName: ~~Color Correction~~ -> The name of the filter applied to the chosen source (for opacity)
> 2. The default canvas dimensions are `1920w x 1080h`. If needed, replace the `canvasWidth` and `canvasHeight` values with the width and height of your OBS canvas.
> 3. In the C# code editor's `References` tab, right click to add all of the required references noted at the bottom of this README.
> 4. Apply a `Color Correction` filter (defaults) to the chosen source, even if you don't plan to use the opacity command. Skipping this step will cause the `!camera` command to fail. 

## Commands
### Preset Positions
Move the chosen source to a preset position, defined by an X and Y coordinate and a key in a C# dictionary.
> `!camera {<top|bottom|mid><left|right>|center}`
> 
> **Example Usages**:
> - `!camera midleft`
> - `!camera center`
> - `!camera topright`

### Specific Coordinates
Move the chosen source to specific X and Y coordinates. **0 is automatically replaced with the `padding` C# variable**
> `!camera {x} {y}`
> 
> **Example Usages**:
> - `!camera 0 100` *Moves to 10, 100*
> - `!camera 0 0` *Moves to 10, 10*

### Movement Along an Axis
Move the chosen source along the specified axis.
> `!camera {+ | -}{amount} {x|y}`
> 
> **Example Usages**:
> - `!camera +50 x` *Moves the source 50px to the right*
> - `!camera -100 y` *Moves the source down by 100px*

### Opacity
Change the opacity of the chosen source. 
> `!camera opacity {0%-100%}`
> 
> **Example Usages**:
> - `!camera opacity 0`
> - `!camera opacity 80%`
> - `!camera opacity 100`

---

### Required References
- mscorlib.dll (.NET)
- System.dll (.NET)
- System.Core.dll (.NET)
- Microsoft.CSharp.dll (.NET)
- Newtonsoft.Json.dll (Streamer.Bot Directory)
