# Efficore

This [Fabric](https://fabricmc.net)-based Minecraft server modpack is meticulously crafted to deliver peak performance and an incredibly smooth gameplay experience. I've fine-tuned server settings, optimized game rules, and incorporated a collection of powerful performance-enhancing mods. Experience lag-free exploration, and seamless world generation. This modpack is designed for players and server administrators who demand the best possible performance from their Minecraft server.

**Key features:**

* **Core Game Optimizations:** Improved performance and security through optimized game rules, server configuration, and enhanced systems. This includes a complex and strategic dynamic view, refined simulation and ticking distances, an enhanced chunk system, improved collision detection, optimized entity tracking, and random ticking for reduced lag.
* **Optimized World Generation:** Faster world loading with pre-generated chunks and improved terrain and structure generation.
* **Network Optimization:** Smoother gameplay through optimized Minecraft networking and lag compensation.
* **Performance and Debug Tools:** Built-in profiling and monitoring tools for diagnosing performance issues, along with improved error reporting for easier troubleshooting.

**Disclaimer:** While this modpack strives to maintain vanilla gameplay as much as possible, some optimizations may affect certain vanilla behaviors. These changes are generally minor and intended to improve performance without significantly altering the core gameplay experience. However, it's essential to be aware of this possibility. If you encounter any unexpected behavior, please report it in the "Contacts" section so it can be investigated.

## Mods List

- The latest Efficore versions includes the mod list: [efficore/versions](https://modrinth.com/modpack/efficore/versions).
- And within the source code of the GitHub project: [meyverick/efficore](https://github.com/meyverick/efficore/tree/main/mods)

## Changelog

A detailed changelog for this modpack is available on GitHub: [meyverick/efficore/changelog.md](https://github.com/meyverick/efficore/blob/main/changelog.md)

This changelog provides a comprehensive history of changes, updates, and bug fixes for each version of the modpack. It's a valuable resource for staying informed about the latest improvements and tracking the evolution of the modpack over time.

## Performance and Debug Tools

This modpack includes tools that help diagnose and understand performance issues, making it easier to identify bottlenecks and optimize the server.

**Performance Profiling:**

A performance profiler is included, which allows for in-depth analysis of server performance. This tool can identify which parts of the game are causing lag or consuming excessive resources. It provides detailed reports on CPU usage, memory allocation, and tick durations, helping pinpoint areas for optimization.

**Server Health Monitoring:**

The modpack also features server health monitoring tools that provide real-time insights into key performance indicators. This includes tracking ticks per second (TPS), CPU usage, memory usage, and disk usage. These metrics help identify potential issues and ensure the server is running smoothly.

**Improved Error Reporting:**

Error messages and crash reports have been enhanced to provide more readable and informative information. This makes it easier to understand the cause of errors and troubleshoot problems effectively.

**Log Sharing with mclo.gs:**

When seeking assistance with server issues or errors, sharing your Minecraft server logs can be invaluable. To easily share your logs while protecting sensitive information, I recommend using [mclo.gs](https://mclo.gs/).

* **Easy Log Upload:** Simply paste your Minecraft log file from any source into mclo.gs. Critical information, such as IP addresses, is automatically hidden.
* **Shareable Short URLs:** mclo.gs generates a personal short URL that you can share with others, facilitating collaborative troubleshooting.
* **Intelligent Log Analysis:** Benefit from intelligent syntax highlighting and analysis to quickly identify potential problems within your Minecraft log.

Using mclo.gs will help you and others quickly understand and resolve any issues you encounter.

### Server Startup Flags

To further optimize server performance, I recommend using the following startup flags with [Zulu JDK 23](https://www.azul.com/downloads/?package=jdk#zulu):

```
-Xms4G -Xmx8G -XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200 -XX:+UnlockExperimentalVMOptions -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:G1NewSizePercent=30 -XX:G1MaxNewSizePercent=40 -XX:G1HeapRegionSize=8M -XX:G1ReservePercent=20 -XX:G1HeapWastePercent=5 -XX:+UseCompressedOops -XX:+OptimizeStringConcat -XX:+UnlockDiagnosticVMOptions -XX:+AlwaysActAsServerClassMachine -XX:NmethodSweepActivity=1 -XX:ReservedCodeCacheSize=400M -XX:NonNMethodCodeHeapSize=12M -XX:ProfiledCodeHeapSize=194M -XX:NonProfiledCodeHeapSize=194M -XX:-DontCompileHugeMethods -XX:MaxNodeLimit=240000 -XX:NodeLimitFudgeFactor=8000 -XX:+UseVectorCmov -XX:+PerfDisableSharedMem -XX:+UseFastUnorderedTimeStamps -XX:+UseCriticalJavaThreadPriority -XX:ThreadPriorityPolicy=1 --enable-native-access=ALL-UNNAMED
```

These flags are designed to improve garbage collection, memory management, and overall server performance. Here's a breakdown of some key flags:

* **`-Xms4G -Xmx8G`**: Sets the initial and maximum heap size to 4GB and 8GB, respectively. Adjust these values based on your server's available RAM.
* **`-XX:+UseG1GC`**: Enables the Garbage-First garbage collector, generally preferred for Minecraft servers.
* **`-XX:+ParallelRefProcEnabled`**: Enables parallel reference processing, improving garbage collection efficiency.
* **`-XX:MaxGCPauseMillis=200`**: Sets a target for maximum garbage collection pause times, aiming to minimize lag spikes.
* **`-XX:+DisableExplicitGC`**: Disables explicit garbage collection calls, allowing the JVM to manage memory more effectively.
* **`-XX:+AlwaysPreTouch`**: Touches all allocated memory pages at startup, potentially improving performance.

**Why Zulu JDK 23?**

[Zulu JDK 23](https://www.azul.com/downloads/?package=jdk#zulu) is a high-performance, open-source Java Development Kit that is well-suited for running Minecraft servers. It is known for its stability, efficiency, and compatibility with Minecraft.

**Important Note:** These flags are suggestions, and their effectiveness may vary depending on your server hardware and configuration. It's recommended to experiment with different settings to find the optimal configuration for your specific environment.

# Configuration

This modpack allows you to customize various settings to fine-tune your server's performance and gameplay experience. Configuration files for the server and mods are located in the `config/yosbr` directory.

**Important Notes:**

* **No Overwriting:** The modpack will not overwrite your existing configuration files. It will only create new config files if they don't already exist. This allows you to keep your custom settings while benefiting from the initial configuration provided by the modpack.
* **Editing Configs:** To change any settings, simply edit the corresponding configuration files in the `config/yosbr` directory using a text editor.

Feel free to explore the configuration files and adjust the settings to your liking. If you have any questions or need assistance, please refer to the "Contacts" section for ways to reach out.

# Contacts

Have you encountered a problem, identified a bug, or experienced a crash while using this modpack? Please don't hesitate to [open an issue](https://github.com/meyverick/efficore/issues) on GitHub. Your detailed reports are invaluable in helping me identify and resolve any issues, ensuring a smoother experience for everyone.

For general discussions, ideas, questions, or if you simply want to share your thoughts and feedback, I encourage you to [open a discussion](https://github.com/meyverick/efficore/discussions) on GitHub. It's a great place to connect with me and other users of the modpack, fostering a community of shared interest in optimized Minecraft gameplay.

### Supporting Open-Source Projects

Open-source projects like this one thrive on community sharing and support. Sharing the modpack with others, providing feedback, and contributing to discussions all help build a strong community. And if you find this modpack valuable and want to contribute to its continued development, consider supporting me or other open-source developers through platforms like GitHub Sponsors.

Sharing is caring, and spreading the word about projects you enjoy helps them grow and reach a wider audience. If you'd like to support my work, you can do so here: [github.com/sponsors/meyverick](https://github.com/sponsors/meyverick).

Every contribution, big or small, makes a difference in helping maintain and improve open-source projects for everyone.

I appreciate your input and look forward to hearing from you!

# Credits

A big thank you to all the mod developers whose hard work and dedication have made this modpack possible. Your contributions to the Minecraft community are greatly appreciated, and your mods have helped create a more optimized and enjoyable gameplay experience.

# Licenses

Copyrights lasts for the life of the author plus an additional 70 years.

This project is protected by the [Berne Convention](https://www.wipo.int/treaties/en/ip/berne/summary_berne.html) and licensed under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0) (the "License").

You may not use this file except in compliance with copyrights.

Unless required by applicable law or agreed to in writing, this project is distributed **"as is" basis, without warranties or conditions of any kind**, either express or implied.

**Important Notes:** I'm dedicated to providing a smooth and optimized Minecraft server experience with this modpack. However, it's important to remember that using any modpack comes with inherent risks. I cannot be held responsible for any unintended consequences, such as world corruption, crashes, or compatibility issues that may arise from using this modpack. Please use it at your own risk and ensure you have backups of your worlds before installing.