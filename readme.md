# Efficore

This [Fabric](https://fabricmc.net)-based Minecraft server modpack is meticulously crafted to deliver peak performance and an incredibly smooth gameplay experience. I've fine-tuned server settings, optimized game rules, and incorporated a collection of powerful performance-enhancing mods. Experience lag-free exploration, seamless world generation, and dynamic view distance adjustment, all without sacrificing visual fidelity.  This modpack is designed for players and server administrators who demand the best possible performance from their Minecraft server.

**Key features:**

* **Dynamic View and Simulation Distance:** Dynamically adjusts view and simulation distances based on server load, ensuring optimal performance without sacrificing visual quality when resources allow.
* **Pre-generated Chunks:** Pre-generates chunks around the world origin and the Ender Dragon fight area to minimize lag during critical moments.
* **Optimized World Generation:** Improved algorithms enhance terrain and structure generation, leading to faster world loading and smoother exploration.
* **Core Game Optimizations:** Enhancements to the chunk system, collision detection, entity tracking, and random ticking further improve server performance and reduce lag.
* **Lag Compensation:** A system compensates for lag by adjusting the timing of certain actions, maintaining a responsive experience even under heavy load.
* **Performance and Debug Tools:** Profiling and monitoring tools help diagnose and address performance bottlenecks, while improved error reporting aids in troubleshooting.

This modpack prioritizes a stable and enjoyable gameplay experience, allowing players to focus on exploration, building, and adventure without the frustration of lag and performance issues.

## Dependencies

- [AdaptiveView](https://modrinth.com/mod/adaptiveview)
- [Alternate Current](https://modrinth.com/mod/alternate-current)
- [Boring Default Game Rules](https://modrinth.com/mod/boring-default-game-rules)
- [Chunky](https://modrinth.com/plugin/chunky)
- [Moonrise](https://modrinth.com/mod/moonrise-opt)
- [Noisium](https://modrinth.com/mod/noisium)
- [spark](https://modrinth.com/mod/spark)
- [StackDeobfuscator](https://modrinth.com/mod/stackdeobf)
- [Structure Layout Optimizer](https://modrinth.com/mod/structure-layout-optimizer)
- [TT20 (TPS Fixer)](https://modrinth.com/mod/tt20)
- [World Border](https://modrinth.com/mod/world-border)
- [Your Options Shall Be Respected (YOSBR)](https://modrinth.com/mod/yosbr)

## Specificities

### Default Server Configuration and Game Rules

**Server Configuration:**

* Spawn chunk protection has been disabled to prevent unnecessary server ticking in the spawn area.
* Network compression threshold has been adjusted to balance CPU usage and bandwidth consumption. This setting determines when packets are compressed, potentially saving server resources.
* View distance, the number of chunks sent to players, is initially set to 7. However, this value is dynamically adjusted by Adaptive View- and Simulation- Distance (see the mentioned section for details).
* Simulation distance, the number of chunks around a player where the server actively simulates events is initially set to 4. This value is also dynamically adjusted. This prioritizes performance by limiting the area of active simulation while allowing for a greater view distance.
* Synchronous chunk writes have been disabled. This can improve performance by allowing the server to write chunk data to disk asynchronously.

**Game Rules:**

* Fire spread has been disabled. This prevents accidental destruction of structures and reduces server load by eliminating fire propagation calculations.
* Elytra movement checks have been disabled. This prevents potential rollbacks and reduces unnecessary server calculations. It's acknowledged that determined cheaters will find ways to bypass checks regardless.
* Player movement checks have been disabled. Similar to elytra checks, this reduces server load and prevents rollbacks.
* Spectator mode will no longer generate new chunks. This reduces unnecessary chunk loading and improves performance.
* Spawn chunks have been disabled. This prevents constant ticking and further enhances server performance.
* Very large world borders have been placed on all worlds. This is primarily to prevent performance loss from excessive chunk loading by players traveling to extreme distances, rather than directly improving performance.

### Adaptive View- and Simulation- Distance

I've implemented a complex and strategic set of rules that dynamically adjust the server's View and Simulation Distance based on real-time performance metrics (MSPT and Memory usage).

### Pre-generates Chunks

Pre-generating chunks with a tool like the Chunky mod in Minecraft servers offers significant performance benefits and an improved player experience.

* The **Overworld** origin has been pre-generated. This ensures a smoother initial exploration experience and reduces server load during gameplay.
* The **Enderworld** origin has been pre-generated. This provides a stable and optimized environment, specifically for the final boss fight, by minimizing lag and ensuring consistent performance during the encounter.
* **Smart Pre-generation:** The pre-generation tasks are automatically paused when players are online. This prevents any potential performance impact on active players and ensures that chunk generation only occurs when server load is minimal.

### World Generation

The world generation in this modpack has been significantly enhanced to provide a smoother and more efficient experience. This is achieved through the integration of specialized optimization mods that improve various aspects of world generation.

* **Optimized Terrain Generation:** The terrain generation algorithm has been improved to reduce lag and speed up block placement when new chunks are created. This results in faster world loading and smoother exploration.
* **Faster Structure Generation:** The generation of complex structures has been optimized to minimize lag spikes. This is achieved by streamlining the process of assembling structure pieces, reducing unnecessary calculations, and improving the efficiency of structure processing.

### Others

This modpack includes a collection of performance enhancements and optimizations that work behind the scenes to improve your gameplay experience. These improvements focus on optimizing various core game mechanics without heavily altering vanilla behavior.

**Key Optimizations:**

* **Enhanced Chunk System:** The way the game handles chunks has been rewritten to improve efficiency and reduce lag. This leads to smoother world loading and less stuttering during gameplay.
* **Collision Optimization:** Collision detection has been optimized to reduce unnecessary calculations. This improves performance, especially in areas with many entities or complex structures.
* **Entity Tracking:** The way the server tracks entities has been improved to reduce server load and improve performance. This is particularly beneficial in situations with many entities, such as large farms or battles.
* **Random Ticking:** The random ticking system, responsible for things like plant growth and block updates, has been optimized to reduce server load and improve performance.
* **Lag Compensation:** The modpack includes a system that compensates for lag by adjusting the timing of certain actions, such as breaking blocks or attacking entities. This helps maintain a smooth and responsive gameplay experience even when the server is under heavy load.

### Performance and Debug Tools

This modpack includes tools that help diagnose and understand performance issues, making it easier to identify bottlenecks and optimize the server.

**Performance Profiling:**

A performance profiler is included, which allows for in-depth analysis of server performance. This tool can identify which parts of the game are causing lag or consuming excessive resources. It provides detailed reports on CPU usage, memory allocation, and tick durations, helping pinpoint areas for optimization.

**Server Health Monitoring:**

The modpack also features server health monitoring tools that provide real-time insights into key performance indicators. This includes tracking ticks per second (TPS), CPU usage, memory usage, and disk usage. These metrics help identify potential issues and ensure the server is running smoothly.

**Improved Error Reporting:**

Error messages and crash reports have been enhanced to provide more readable and informative information. This makes it easier to understand the cause of errors and troubleshoot problems effectively.

### Server Startup Flags

To further optimize server performance, I recommend using the following startup flags with Zulu JDK 23:

```
-Xms4G -Xmx8G -XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200 -XX:+UnlockExperimentalVMOptions -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:G1NewSizePercent=30 -XX:G1MaxNewSizePercent=40 -XX:G1HeapRegionSize=8M -XX:G1ReservePercent=20 -XX:G1HeapWastePercent=5 -XX:+UseCompressedOops -XX:+OptimizeStringConcat -XX:+UnlockDiagnosticVMOptions -XX:+AlwaysActAsServerClassMachine -XX:NmethodSweepActivity=1 -XX:ReservedCodeCacheSize=400M -XX:NonNMethodCodeHeapSize=12M -XX:ProfiledCodeHeapSize=194M -XX:NonProfiledCodeHeapSize=194M -XX:-DontCompileHugeMethods -XX:MaxNodeLimit=240000 -XX:NodeLimitFudgeFactor=8000 -XX:+UseVectorCmov -XX:+PerfDisableSharedMem -XX:+UseFastUnorderedTimeStamps -XX:+UseCriticalJavaThreadPriority -XX:ThreadPriorityPolicy=1
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

I appreciate your input and look forward to hearing from you!

# Credits

A big thank you to all the mod developers whose hard work and dedication have made this modpack possible. Your contributions to the Minecraft community are greatly appreciated, and your mods have helped create a more optimized and enjoyable gameplay experience.

# Licenses

This project is protected by the [Berne Convention](https://www.wipo.int/treaties/en/ip/berne/summary_berne.html) and released under the [ISC License](https://opensource.org/license/isc-license-txt) licence. Copyright protection lasts for the life of the author plus an additional 70 years.