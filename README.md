# SecuriCore-Documentation

```markdown
# SecuriCore Documentation

## Overview

BTGuard is a comprehensive security library designed to provide various protective measures for applications. The library includes features such as webhook integration, anti-injection mechanisms, anti-debugging measures, virtual machine detection, and more. Below are the details and functionalities of each method provided by the BTGuard class.

## Constructor

### BTGuard(string key)
Initializes a new instance of the BTGuard class using a provided security key.

```csharp
BTGuard.BTGuard guard = new BTGuard.BTGuard("your-security-key");
```

- **Parameters:**
  - `key` (string): The security key used to initialize the BTGuard instance.

## Methods

### SendToWebhook(bool send)
Enables or disables sending security alerts to a configured webhook.

```csharp
guard.SendToWebhook(true);
```

- **Parameters:**
  - `send` (bool): If set to `true`, security alerts will be sent to the configured webhook.

### SetDiscordWebhook(string webhook, string username)
Sets the Discord webhook URL and the username for sending alerts.

```csharp
guard.SetDiscordWebhook("https://discord.com/api/webhooks/your-webhook-url", "YourUsername");
```

- **Parameters:**
  - `webhook` (string): The Discord webhook URL.
  - `username` (string): The username to be displayed when sending alerts to Discord.

### IsNPCAPInstalled() -> bool
Checks if NPCAP is installed on the system.

```csharp
bool isInstalled = guard.IsNPCAPInstalled();
Console.WriteLine($"NPCAP Installed: {isInstalled}");
```

- **Returns:**
  - `bool`: Returns `true` if NPCAP is installed, otherwise returns `false`.

### EnableAntiInjection()
Enables anti-injection mechanisms to protect the application from code injection attacks.

```csharp
guard.EnableAntiInjection();
```

### PreventDumping()
Prevents the application from being dumped to avoid unauthorized access to its code.

```csharp
guard.PreventDumping();
```

### EnableAntiDebug()
Enables anti-debugging measures to prevent the application from being debugged or tampered with.

```csharp
guard.EnableAntiDebug();
```

### EnableProgramDetection()
Enables detection of unauthorized programs or processes that may interfere with the application.

```csharp
guard.EnableProgramDetection();
```

### DetectVM() -> bool
Detects if the application is running inside a virtual machine.

```csharp
bool isVM = guard.DetectVM();
Console.WriteLine($"Running in VM: {isVM}");
```

- **Returns:**
  - `bool`: Returns `true` if a virtual machine is detected, otherwise returns `false`.

### TurnOffMonitor()
Turns off the monitor as a security measure.

```csharp
guard.TurnOffMonitor();
```

### ToggleMouse(bool enable)
Enables or disables mouse input.

```csharp
guard.ToggleMouse(false);
```

- **Parameters:**
  - `enable` (bool): If set to `true`, mouse input will be enabled; if set to `false`, mouse input will be disabled.

### TriggerBSOD()
Triggers a Blue Screen of Death (BSOD) as an extreme security measure.

```csharp
guard.TriggerBSOD();
```

## Example Usage

```csharp
using BTGuard;

class Program
{
    static void Main(string[] args)
    {
        BTGuard guard = new BTGuard("your-security-key");

        guard.SetDiscordWebhook("https://discord.com/api/webhooks/your-webhook-url", "YourUsername");
        guard.SendToWebhook(true);

        if (guard.IsNPCAPInstalled())
        {
            Console.WriteLine("NPCAP is installed.");
        }

        guard.EnableAntiInjection();
        guard.PreventDumping();
        guard.EnableAntiDebug();
        guard.EnableProgramDetection();

        if (guard.DetectVM())
        {
            Console.WriteLine("Running in a virtual machine.");
        }

        guard.TurnOffMonitor();
        guard.ToggleMouse(false);
        guard.TriggerBSOD();
    }
}
```

## Notes
- Ensure to replace `"your-security-key"` and `"https://discord.com/api/webhooks/your-webhook-url"` with actual values.
- Use the provided methods with caution, especially `TurnOffMonitor`, `ToggleMouse`, and `TriggerBSOD`, as they can significantly affect the user experience.

