# Account Changer

**Account Changer** is a powerful Spigot server-side plugin designed to enhance player convenience. It allows users to seamlessly switch their Minecraft accounts *in-game* via an intuitive GUI, eliminating the need to disconnect or use any client-side modifications. This plugin is useful for accounts management in offline servers, since it is designed originally for offline servers.

### Key Features
- **In-Game Account Switching**: Change accounts directly from the server using a graphical interface.
- **No Client Modifications Required**: Fully server-side, ensuring ease of use and compatibility.
- **Requirements**: [**ProtocolLib**](https://github.com/dmulloy2/ProtocolLib "ProtocolLib"), **Spigot/Paper 1.20.1+**(tested for **1.20.1** and **1.21.3**).

### Getting Started
Before using the plugin, ensure you’ve read the [Installation](#installation) and [Configuration](#configuration) guides for proper setup. 

**1. Commands**

 - `/ac reload` reload the configs in plugin folder.

 - `/ac clear`if without player at the end, clear command sender's status, alias. if with player, clear the target player's status,alias.

 - `/ac switch` open graphic interface for switch the account in game.

 - `/ac help` shows help.

**2.Logic**
 - Original Account not in the list are required to choose the account to login, the alias account chosen previously will not be expire and the original account will always direct to the alias account chosen until a `/ac switch` to another account is performed or a `ac clear` is performed.
 - The Account in the list will be able to change their account also.
 - There's no time limit after choosing the account

Unlock a new level of flexibility for your server players today with **Account Changer**!



## Demo
The GIFs and demonstrations below showcase the functionality of the plugin using the `config.yml` settings provided in the **Configuration** section.

##### With account ABC:
![ABC](https://github.com/user-attachments/assets/20f53043-cf54-49ec-bab3-dfd4bbe28a82)

##### With account BCD, changing to ABC:
![BCD](https://github.com/user-attachments/assets/247d70ff-aaf7-4247-8c15-601116bf84c1)

Originally, the plugin is designed for bedrock-java both sided server, as bedrock players cannot change their names. If you are also using geyser plugin, try this out!


## Installation

This plugin requires [ProtocolLib](https://github.com/dmulloy2/ProtocolLib "ProtocolLib"). To set it up:

1. Download **ProtocolLib** and place it in the `plugins` folder of your server directory.
2. Download `AccountChanger-x.x-xxxx.jar` from the [latest release](https://github.com/mrxzac/AccountChanger/releases/latest "latest release") and place it in the same `plugins` folder.
3. Restart your server to load the plugins.

#### Notice
For servers using authentication plugins during login, this plugin only supports [AuthMe](https://www.spigotmc.org/resources/authmereloaded.6269/ "AuthMe"). You will need to modify `config.yml` in **AuthMe** to ensure compatibility:

##### Update these configs
- Update the `UnrestrictedInventories` section in your `config.yml` . e.g.

```yaml
.....
    # UnrestrictedInventories:
    # - 'myCustomInventory1'
    # - 'myCustomInventory2'
    UnrestrictedInventories: ["Choose Your Account"]
  security:
    # Minimum length of password
    minPasswordLength: 5
.....
```

- add 
```yaml
      - /ac
      - /accountchanger
``` 
to `allowCommands` to help the players in unauthorized status be able to switch account. e.g.
```yaml
 # Hide the chat log from players who are not authenticated?
    hideChat: false
    # Allowed commands for unauthenticated players
    allowCommands:
      - /ac
      - /accountchanger
      - /login
      - /log
      - /l
```

## Configuration

Configuring this plugin is straightforward. The configuration file, `config.yml`, is located in the `\Plugin\AccountChanger` directory. It contains three main parameters for customization.  

```yaml
Players:
  - ABC
MaxPlayers: 20
MaxWait: 10
```
#### Configuration Parameters

1. **`Players`**  
   - This section contains a list of players, each entry starting with `-`.  
   - Players listed here will **log in directly** without going through any account selection steps.  
   - Players **not listed** will be presented with a GUI to **choose an account** from the available options.

2. **`MaxPlayer`**  
   - An integer that sets the **maximum number of player accounts** available to choose from.  
   - Determines the **GUI window size** (number of inventory slots).

3. **`MaxWait`**
   - **Deprecated**



## Acknowledgments  
Special thanks to [ProtocolLib](https://github.com/dmulloy2/ProtocolLib) by **dmulloy2** for making this plugin possible.



## License  
This repository is licensed under the **GNU General Public License v3.0**.  
For more details, see the [LICENSE](LICENSE) file.

