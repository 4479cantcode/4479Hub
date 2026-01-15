## Supported Elements
- Window  
- Tab  
- Section
- Toggle  
- Button  
- Slider  
- Textbox
- Dropdown  
- Keybind
- Colorpicker
- Divider  
- Label
- Watermark
- Notification

## Load Library
```lua
local Bracket = loadstring(game:HttpGet("https://raw.githubusercontent.com/4479cantcode/4479-Hub/refs/heads/main/Library/MainLib/Bracket.lua"))()
```

## Notifications
```lua
Bracket:Push({
    Title = "Success",
    Description = "Script loaded successfully!",
    Duration = 10,
    Callback = function()
        print("Notification closed")
    end
})

Bracket:Push({
    Title = "Auto Farm",
    Description = "Successfully started auto farming"
})
```

## Basic Usage

### Create Window
```lua
local Window = Bracket:Window({
    Name = "My Script Hub",
    Enabled = true,
    Color = Color3.new(1, 0.5, 0.25),
    Size = UDim2.new(0, 496, 0, 496),
    Position = UDim2.new(0.5, -248, 0.5, -248)
})
```

### Window Properties
```lua
Window.Name = "New Name"
Window.Size = UDim2.new(0, 496, 0, 496)
Window.Position = UDim2.new(0.5, -248, 0.5, -248)
Window.Color = Color3.new(1, 0.5, 0.25)
Window.Enabled = true
Window.Blur = true
```

### Background Customization
```lua
Window.Background.ImageTransparency = 0
Window.Background.ImageColor3 = Color3.new(0, 0, 0)
Window.Background.Image = "rbxassetid://5553946656"
```

### Watermark
```lua
local Watermark = Window:Watermark({
    Title = "Bracket V3.3 | My Script",
    Flag = "UI/Watermark/Position",
    Enabled = true
})

Watermark.Enabled = true
Watermark.Title = "New Text"
Watermark.Value = {0, 0, 0, 0}
```

### Create Tabs
```lua
local Tab = Window:Tab({Name = "Main"})
```

## Elements

### Divider
```lua
local Divider = Tab:Divider({
    Text = "Section Name",
    Side = "Left"
})

Divider.Text = "New Text"
```

### Label
```lua
local Label = Tab:Label({
    Text = "Information text",
    Side = "Left"
})

Label.Text = "Updated text"
```

### Button
```lua
local Button = Tab:Button({
    Name = "Click Me",
    Side = "Left",
    Callback = function()
        print("Button clicked!")
    end
})

Button.Name = "New Name"
Button.Callback = function() end
Button:ToolTip("Hover text")
```

### Toggle
```lua
local Toggle = Tab:Toggle({
    Name = "Enable Feature",
    Flag = "Toggle",
    Side = "Left",
    Value = false,
    Callback = function(value)
        print("Toggle state:", value)
    end
})

Toggle.Name = "New Name"
Toggle.Value = true
Toggle.Callback = function(value) end
Toggle:ToolTip("Hover text")
```

### Toggle with Keybind
```lua
local ToggleKeybind = Toggle:Keybind({
    Flag = "Toggle/Keybind",
    Value = "NONE",
    DoNotClear = false,
    Mouse = false,
    Callback = function(key, pressed, toggled)
        print(key, pressed, toggled)
    end,
    Blacklist = {"W", "A", "S", "D", "Slash", "Tab", "Backspace", "Escape", "Space", "Delete", "Unknown", "Backquote"}
})

ToggleKeybind.Value = "B"
ToggleKeybind.Callback = function(key, pressed, toggled) end
```

### Toggle with Colorpicker
```lua
local ToggleColorpicker = Toggle:Colorpicker({
    Flag = "Toggle/Colorpicker",
    Value = {1, 1, 1, 0, false},
    Callback = function(hsvar, color3)
        print(hsvar, color3)
    end
})

ToggleColorpicker.Value = {1, 1, 1, 0, false}
ToggleColorpicker.Callback = function(hsvar, color3) end
```

### Slider
```lua
local Slider = Tab:Slider({
    Name = "Speed",
    Flag = "Slider",
    Side = "Left",
    Min = 0,
    Max = 100,
    Value = 50,
    Precise = 2,
    Unit = "",
    Callback = function(value)
        print("Slider value:", value)
    end
})

Slider.Name = "New Name"
Slider.Value = 75
Slider.Callback = function(value) end
Slider:ToolTip("Hover text")
```

### Textbox
```lua
local Textbox = Tab:Textbox({
    Name = "Input",
    Flag = "Textbox",
    Side = "Left",
    Value = "Default Text",
    Placeholder = "Enter text...",
    NumberOnly = false,
    Callback = function(text, enterPressed)
        print(text, enterPressed)
    end
})

Textbox.Name = "New Name"
Textbox.Value = "New Text"
Textbox.Placeholder = "New Placeholder"
Textbox.Callback = function(text, enterPressed) end
Textbox:ToolTip("Hover text")
```

### Keybind
```lua
local Keybind = Tab:Keybind({
    Name = "Hotkey",
    Flag = "Keybind",
    Side = "Left",
    Value = "NONE",
    Mouse = false,
    DoNotClear = false,
    Callback = function(key, pressed, toggled)
        print(key, pressed, toggled)
    end,
    Blacklist = {"W", "A", "S", "D", "Slash", "Tab", "Backspace", "Escape", "Space", "Delete", "Unknown", "Backquote"}
})

Keybind.Name = "New Name"
Keybind.Value = "B"
Keybind.Callback = function(key, pressed, toggled) end
Keybind:ToolTip("Hover text")
```

### Dropdown
```lua
local Dropdown = Tab:Dropdown({
    Name = "Select Option",
    Flag = "Dropdown",
    Side = "Left",
    List = {
        {
            Name = "Head",
            Mode = "Toggle",
            Value = false,
            Callback = function(selected)
                print("Head selected:", selected)
            end
        },
        {
            Name = "HumanoidRootPart",
            Mode = "Button",
            Value = false,
            Callback = function(selected)
                print("HumanoidRootPart selected:", selected)
            end
        }
    }
})

Dropdown.Name = "New Name"
Dropdown.Value = {"Head"}
Dropdown:BulkAdd(listTable)
Dropdown:AddOption(optionTable)
Dropdown:RemoveOption("OptionName")
Dropdown:Clear()
Dropdown:ToolTip("Hover text")
```

### Colorpicker
```lua
local Colorpicker = Tab:Colorpicker({
    Name = "Color",
    Flag = "Colorpicker",
    Side = "Left",
    Value = {1, 1, 1, 0, false},
    Callback = function(hsvar, color3)
        print(hsvar, color3)
    end
})

Colorpicker.Name = "New Name"
Colorpicker.Value = {1, 1, 1, 0, false}
Colorpicker.Callback = function(hsvar, color3) end
Colorpicker:ToolTip("Hover text")
```

### Section
```lua
local Section = Tab:Section({
    Name = "Section Name",
    Side = "Right"
})

Section.Name = "New Name"

Section:Divider()
Section:Label()
Section:Button()

local Toggle = Section:Toggle()
Toggle:Keybind()
Toggle:Colorpicker()

Section:Slider()
Section:Textbox()
Section:Keybind()
Section:Dropdown()
Section:Colorpicker()
```

## Configs Example
```lua
local ConfigSection = Tab:Section({
    Title = "Configuration",
    Side = "Left"
})

local ConfigName = ConfigSection:Textbox({
    Title = "Config Name",
    Default = "",
    Placeholder = "Enter config name..."
})

ConfigSection:Button({
    Title = "Save Config",
    Callback = function()
        if ConfigName.Value == "" then return end
        
        local ConfigData = {}
        for Flag, Element in pairs(Bracket.Flags) do
            ConfigData[Flag] = Element.Value
        end
        
        local FolderName = "4479Hub"
        if not isfolder(FolderName) then makefolder(FolderName) end
        if not isfolder(FolderName .. "/Configs") then makefolder(FolderName .. "/Configs") end
        
        writefile(FolderName .. "/Configs/" .. ConfigName.Value .. ".json", 
                 HttpService:JSONEncode(ConfigData))
    end
})

ConfigSection:Button({
    Title = "Load Config",
    Callback = function()
        if ConfigName.Value == "" then return end
        
        local FolderName = "4479Hub"
        local Success, Data = pcall(function()
            return HttpService:JSONDecode(
                readfile(FolderName .. "/Configs/" .. ConfigName.Value .. ".json")
            )
        end)
        
        if Success and Data then
            for Flag, Value in pairs(Data) do
                if Bracket.Flags[Flag] then
                    Bracket.Flags[Flag]:Set(Value)
                end
            end
        end
    end
})

ConfigSection:Button({
    Title = "Delete Config",
    Callback = function()
        if ConfigName.Value == "" then return end
        
        local FolderName = "4479Hub"
        local FilePath = FolderName .. "/Configs/" .. ConfigName.Value .. ".json"
        
        if isfile(FilePath) then
            delfile(FilePath)
        end
    end
})

local ConfigDropdown = ConfigSection:Dropdown({
    Title = "Select Config",
    List = Bracket.Utilities:GetConfigs("4479Hub"),
    Callback = function(Value)
        ConfigName:Set(Value)
    end
})

ConfigSection:Button({
    Title = "Refresh List",
    Callback = function()
        ConfigDropdown:Set(Bracket.Utilities:GetConfigs("4479Hub"))
    end
})
```

## Complete Example
```lua
local Bracket = loadstring(game:HttpGet("https://raw.githubusercontent.com/4479cantcode/4479-Hub/refs/heads/main/Library/MainLib/Bracket.lua"))()

Bracket:Push({
    Title = "Success",
    Description = "Script loaded successfully!",
    Duration = 10,
    Callback = function()
        print("Notification closed")
    end
})

local Window = Bracket:Window({
    Name = "Example Hub",
    Enabled = true,
    Color = Color3.new(1, 0.5, 0.25),
    Size = UDim2.new(0, 496, 0, 496),
    Position = UDim2.new(0.5, -248, 0.5, -248)
})

local Watermark = Window:Watermark({
    Title = "Example Hub | v1.0",
    Flag = "UI/Watermark/Position",
    Enabled = true
})

local MainTab = Window:Tab({Name = "Main"})

MainTab:Divider({Text = "Features", Side = "Left"})

MainTab:Toggle({
    Name = "Auto Farm",
    Flag = "AutoFarm",
    Side = "Left",
    Value = false,
    Callback = function(value)
        print("Auto Farm:", value)
    end
})

MainTab:Slider({
    Name = "Farm Speed",
    Flag = "FarmSpeed",
    Side = "Left",
    Min = 1,
    Max = 10,
    Value = 5,
    Precise = 1,
    Unit = "x",
    Callback = function(value)
        print("Speed:", value)
    end
})

MainTab:Dropdown({
    Name = "Target Part",
    Flag = "TargetPart",
    Side = "Left",
    List = {
        {
            Name = "Head",
            Mode = "Button",
            Callback = function()
                print("Head selected")
            end
        },
        {
            Name = "Torso",
            Mode = "Button",
            Callback = function()
                print("Torso selected")
            end
        }
    }
})

local SettingsTab = Window:Tab({Name = "Settings"})

SettingsTab:AddConfigSection("MyScript", "Left")

local Section = SettingsTab:Section({Name = "UI Settings", Side = "Right"})

local UIToggle = Section:Toggle({
    Name = "UI Enabled",
    Flag = "UI/Enabled",
    Value = true,
    Callback = function(value)
        Window.Enabled = value
    end
})

UIToggle:Keybind({
    Flag = "UI/Keybind",
    Value = "RightShift",
    DoNotClear = true
})

UIToggle:Colorpicker({
    Flag = "UI/Color",
    Value = {1, 0.25, 1, 0, true},
    Callback = function(hsvar, color)
        Window.Color = color
    end
})

Window:AutoLoadConfig("MyScript")
```

## Notes

- **Side Parameter**: Can be "Left", "Right" or nil (auto-choose)
- **Flag System**: Used for saving/loading configs
- **HSVAR Format**: {Hue, Saturation, Value, Alpha, Rainbow}
- **Keybind Blacklist**: Prevents certain keys from being bound
- **DoNotClear**: Keybind won't be cleared when clicking "Clear" button
- **IgnoreFlag**: Element won't be saved in configs
- **HideName**: Hides the element's name label
- **Wide**: Makes sliders take full width
