# Lantern-PC concept

Lantern-PC is an innovative computer project that replaces a traditional screen with a high-speed RGB LED lantern grid.  
It achieves ultra-high frame rates (over 100,000 FPS) and near-zero latency, creating a smooth and futuristic visual experience.

## Features

- Uses hundreds of addressable RGB LED lanterns as pixels
- Controlled by an FPGA for extremely fast updates
- Achieves refresh rates beyond conventional monitors
- Ultra-low latency input-to-display response
- Runs standard PC software (Windows, games) through a custom rendering pipeline
- Optional surround sound and startup animations

## 🧠 How Lantern-PC Works
Lantern-PC is a breakthrough display technology that replaces traditional monitors with a custom grid of RGB LED lanterns controlled by an FPGA and CPU. It achieves ultra-high frame rates (100,000+ FPS) and near-zero input latency using parallel hardware and custom software.

🔷 System Overview
Rendering the Image

The CPU renders frames just like a regular PC — calculating the color (RGB) for each pixel in the image.

These RGB values (24-bit: 8 bits per Red, Green, Blue) are stored in system memory as a frame buffer.

Data Transfer to FPGA

Instead of sending the image to a GPU/monitor, the frame is sent to a fast, programmable FPGA chip.

The FPGA reads the RGB data and prepares it for output.

Parallel Output to Lanterns

The FPGA uses multiple parallel SPI lanes (30–40 MHz or more) to send RGB data directly to thousands of micro RGB lanterns.

All lanterns update in perfect sync using shared latch/clock signals.

Each lantern lights up with its assigned RGB value, forming a real-time image.

High FPS Display

The lanterns can update at over 100,000 frames per second, much faster than any traditional screen.

The result is ultra-smooth motion with almost zero blur or delay.

Low-Latency Input

Custom keyboard and mouse hardware operate at 100,000 Hz polling rate, directly connected to the FPGA.

Inputs are processed instantly (in ~10–20µs), bypassing OS/USB bottlenecks.

This makes Lantern-PC ideal for gaming, simulation, and real-time control.

Power Efficiency

Power usage is mostly determined by brightness, not frame rate.

~7.5W at 25% brightness

~15W at 50% brightness

~30W at 100% brightness

FPGA power adds ~3–7W depending on workload.

Rendering Approach

Lantern-PC uses efficient software rendering with flat shading and fixed-point math.

No traditional GPU is required — 3D and 2D images can be rendered by the CPU and/or FPGA logic.

✅ Summary
The CPU renders the image → stores it as RGB in memory → sends it to the FPGA → FPGA updates all lanterns in parallel → lanterns display the image in real-time.

Input devices also connect directly to the FPGA → enabling instant reaction at 100,000 Hz.

The result: a fast, smooth, modular display system with massive potential beyond traditional screens.

## How to Build Lantern-PC

To build your own Lantern-PC, follow these basic steps:

1. **Get the LED Lanterns**  
   Acquire addressable RGB LED modules such as SK9822 or LPD8806. Arrange them into a physical grid that will act as the display.

2. **Set up the Controller**  
   Use an FPGA development board to drive the LED lanterns. Program the FPGA to send data signals at very high speed (100,000+ updates per second) via SPI or similar protocols.

3. **Prepare the PC Hardware**  
   Use a small form-factor PC (like Mini-ITX) running Windows or Linux to handle software, input, and game processing.

4. **Connect Input Devices**  
   Use ultra-high polling rate mouse and keyboard (100,000 Hz) connected to the PC for low-latency control.

5. **Wire Everything**  
   Connect the FPGA controller to the LED grid with proper wiring, including short cables, resistors, and shared latch signals for synchronization.

6. **Develop or Use Software**  
   Run custom rendering software that converts game frames or UI elements into LED color data and sends it to the FPGA controller.

7. **Power the System**
Power-On Behavior:

Pressing the power button turns on the PC, FPGA, and lanterns.

The system boots into Windows and shows UI via the lantern display.

An optional boot animation can pulse across the lanterns to indicate startup.

Power-Off Behavior:

Pressing the power button again safely shuts down Windows and turns off the lanterns.

Soft Reset:

Hold the power button for 5 seconds to trigger a soft reset of the entire system.

Optional Sleep Mode:

Lanterns dim or turn off.

RAM and system state are preserved.

Instant wake-on-input.

Surge/Battery Protection (Optional):

Prevent data loss with a backup battery or UPS.

Can trigger safe shutdown during outages.

Visual Indicators:

Use lanterns to show status animations like errors, sleep mode, or ready state.
 
## Contribution

Contributions and suggestions are welcome!  
Please open an issue or submit a pull request.

## License

This project is open-source and licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

**Created by Dan Raitburg**

Contact: danrait1 [at] gmail [dot] com




