# Weekter ⏳

**Weekter** is a lightweight C++ command-line tool for tracking weekly working hours.
It logs start/end times, calculates progress toward a weekly goal, and shows desktop notifications.

## Features
- ⏱️ Start and stop work sessions with a toggle command
- 📊 Calculate total worked hours this week
- 🔄 Show remaining time until weekly target
- 📝 Logs stored in `~/Mega/Job/Hours/<filename>.txt`
- 🔔 Desktop notifications via `notify-send` (Linux)

## Arguments
The program expects **4 arguments** (after the executable name):

1. **Name** → A label for the session (e.g., `ProjectX`)
2. **Filename** → File used to store logs (e.g., `work.txt`)
3. **Weekly hours** → Target in hours (e.g., `20`)
4. **Mode** → Either:
   - `t` → toggle start/end of a session
   - `s` → show current status without changing logs

Example:
```bash
./weekter "ProjectX" "work.txt" 20 t
```

## Example Usage
- Start working:
  ```bash
  ./weekter "Study" "study.txt" 15 t
  ```
- Stop working:
  ```bash
  ./weekter "Study" "study.txt" 15 t
  ```
- Show status (time worked, last session, remaining time):
  ```bash
  ./weekter "Study" "study.txt" 15 s
  ```

## Notifications
Weekter uses `notify-send` to display progress:
- ✅ Total time worked this week
- ⏳ Last session duration
- 🕒 Time left until target is reached

## File Storage
Logs are stored in:
```
~/Mega/Job/Hours/<filename>.txt
```

Each line contains:
```
timestamp S/F name worked_time time_and_date [Finished]
```

- `S` → session start
- `F` → session finish

## Requirements
- Linux with `notify-send`
- C++11 or newer
- Standard libraries: `<ctime>`, `<fstream>`, `<vector>`, `<sys/stat.h>`

