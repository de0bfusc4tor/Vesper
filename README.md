# 𝖁𝖊𝖘𝖕𝖊𝖗

> _Effects Pedals controller for the M5Stack Cardputer. Quantized and rhythmic interface for MIDI control._

![Under Development](https://img.shields.io/badge/Status-Under%20Development-orange)
![Architecture](https://img.shields.io/badge/Architecture-ESP32--S3-black?labelColor=606060&style=flat-square)
![DAW](https://img.shields.io/badge/DAW-Ableton%20Live%2012%2B-000000?style=flat-square&logo=abletonlive&logoColor=white)
![Format](https://img.shields.io/badge/Format-Binary-00CED1?style=flat-square)
![Hardware](https://img.shields.io/badge/Hardware-M5Stack%20Cardputer-white?style=flat-square&logo=espressif&logoColor=red)

---

## 𝐅𝐞𝐚𝐭𝐮𝐫𝐞𝐬

- **Ableton Link Sync**: Phase synchronization with DAWs and Ableton Link enabled hardware over 2.4GHz Wi-Fi.
- **Quantized MIDI Engine**: Arm MIDI commands and trigger them with surgical precision on the next beat or bar boundary.
- **Optimized UI**: Minimalist black and teal interface custom-built for the Cardputer’s 240x135 display.
- **Physical MIDI Bridge**: Acts as a rhythmic hub between your computer's DAW and external MIDI-enabled effects pedals.
- **Dual Performance Modes**: Switch instantly between Quantized (rhythmic) and Instant (raw) trigger modes.

---

## 𝐒𝐲𝐬𝐭𝐞𝐦 𝐑𝐞𝐪𝐮𝐢𝐫𝐞𝐦𝐞𝐧𝐭𝐬

- **Hardware**: [M5Stack Cardputer](https://docs.m5stack.com/en/core/Cardputer) (ESP32-S3).
- **Network**: 2.4GHz Wi-Fi environment for Ableton Link.
- **Deployment**: Arduino IDE for firmware build.
- **DAW**: Ableton Live 12+

---

## 𝐈𝐧𝐬𝐭𝐚𝐥𝐥𝐚𝐭𝐢𝐨𝐧

### 𝟏. 𝐄𝐧𝐯𝐢𝐫𝐨𝐧𝐦𝐞𝐧𝐭 𝐒𝐞𝐭𝐮𝐩
1. Open Arduino IDE and install the **ESP32** board manager.
2. Select **ESP32-S3 Dev Module** (or M5Stack Cardputer).
3. Install the following libraries via the Library Manager:
   - `M5Cardputer`
   - `AbletonLink`
   - `USB`

### 𝟐. 𝐂𝐨𝐧𝐟𝐢𝐠𝐮𝐫𝐚𝐭𝐢𝐨𝐧
1. Open `vesper_controller.ino`.
2. Locate the Wi-Fi section and update the credentials:
   ```cpp
   char ssid[] = "WIFI_SSID";
   char pass[] = "WIFI_PASS";
   ```

### 𝟑. 𝐃𝐞𝐩𝐥𝐨𝐲𝐦𝐞𝐧𝐭
1. Connect the `Cardputer` via USB-C.
2. Compile and Upload the sketch.
3. Once the teal interface appears, `Vesper` is ready to sync.

---

## 𝐒𝐲𝐧𝐜 & 𝐑𝐨𝐮𝐭𝐢𝐧𝐠

### 𝐀𝐛𝐥𝐞𝐭𝐨𝐧 𝐋𝐢𝐧𝐤 𝐒𝐲𝐧𝐜
Ensure the Cardputer and your computer are on the same Wi-Fi network. Enable **Link** in `Ableton Live`'s top-left corner. `Vesper` will automatically detect the session and synchronize its internal phase bar to the project BPM.

### 𝐌𝐈𝐃𝐈 𝐇𝐮𝐛 𝐖𝐨𝐫𝐤𝐟𝐥𝐨𝐰
1. **Routing**: Create a MIDI track in your DAW for each hardware pedal.
2. **Input**: Set `MIDI From` to `Vesper (USB MIDI)`.
3. **Output**: Set `MIDI To` to your hardware pedal's interface.
4. **Execution**: When `Vesper` sends a CC, it is held until the next bar line, ensuring your pedal's state changes (like a Reverb Freeze) happen exactly on the downbeat.

---

## 𝐂𝐨𝐧𝐭𝐫𝐨𝐥𝐬

### 𝐊𝐞𝐲𝐛𝐨𝐚𝐫𝐝 𝐌𝐚𝐩𝐩𝐢𝐧𝐠

| Key | Action | Key | Action |
|:---:|:---:|:---:|:---:|
| **1 - 8** | Select Active Pedal | **;** | Increase Primary CC |
| **.** | Decrease Primary CC | **Space** | Global Freeze (Quantized) |
| **Tab** | Toggle Quantized/Instant | **Enter** | Re-sync Phase |

### 𝐎𝐧-𝐒𝐜𝐫𝐞𝐞𝐧 𝐏𝐚𝐫𝐚𝐦𝐞𝐭𝐞𝐫𝐬

- **Mode Indicator**: Displays **[Q]** for Quantized or **[I]** for Instant mode.
- **BPM**: Real-time tempo readout from the Link session.
- **Active Pedal**: Shows the name and MIDI value of the currently selected device.
- **Phase Bar**: A 4-beat visual progress bar indicating the current bar's position.

---

_This firmware is free. Don't forget to give it a ⭐ on Github if you find it useful for your performance._

---

<p align="center"><code>𝕯𝖊𝖔𝖇𝖋𝖚𝖘𝖈𝖆𝖙𝖊</code></p>
<p align="center">2026</p>
