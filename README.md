# Cinema Ticket Booking (C++)

A small, simple console-based cinema ticket booking application written in modern C++ (C++17/C++20 compatible). This README includes build and run instructions tailored for a minimal C++ project, plus localization in English and Bahasa Indonesia.

### Features
- List available movies and schedules
- View and select seats in a simple seat map
- Create bookings and save them to a file
- Basic command-line user interface
- Simple validation of seat availability

(Actual feature set depends on the repository implementation. Adjust as needed.)

### Requirements
- A C++ compiler supporting C++17 or newer (g++ 7+, clang 6+, MSVC 2017+)
- CMake (optional, recommended) or make, or just a compiler to build a single-file demo
- Standard C++ library (no heavy external dependencies expected)
- (Optional) CPack or additional tooling for packaging

### Build & Run

Below are three typical ways to build and run the project depending on how the repository is organized.

1) Using CMake (recommended if CMakeLists.txt exists)
```bash
mkdir -p build
cd build
cmake .. -DCMAKE_BUILD_TYPE=Release
cmake --build . --config Release
# Example executable name: cinema
./cinema
```

2) Using a Makefile (if provided)
```bash
# from repo root
make
# run the produced executable (example)
./bin/cinema
```

3) Single-file / quick compile (for small demos)
```bash
g++ -std=c++17 -O2 -Wall -Wextra -o cinema src/main.cpp
./cinema
```

Windows (Visual Studio)
- Open the provided solution or create a new Visual Studio project and add source files.
- Set C++ language standard to C++17 or later and build.

### Configuration
- If the app reads/writes bookings to a file, check `.env`, `config.json`, or constants in source code for file path settings.
- Modify compile flags or CMake options to enable debug builds, sanitizers, or tests:
  - For address/sanitizer debugging with GCC/Clang: add -fsanitize=address,undefined -g

### Running examples
- Start the program, follow prompts to list movies, choose a schedule, view seat map, and book seats.
- After booking, check the bookings file (e.g., `data/bookings.json` or `bookings.txt`) to confirm persistence.

### Testing
- If unit tests exist (Catch2, Google Test, etc.), build the test target:
```bash
# example with CMake
cmake -S . -B build -DBUILD_TESTS=ON
cmake --build build --target tests
./build/tests
```
- If no testing framework is included, add simple test harnesses or assertion-based checks.

### Project structure (example)
```
/src
  main.cpp
  app.cpp
  app.h
  movie.cpp
  movie.h
  schedule.cpp
  schedule.h
  seatmap.cpp
  seatmap.h
/tests
  ...
/data
  movies.json
  bookings.json
/CMakeLists.txt
/Makefile
/README.md
```

### Contributing
1. Fork the repository
2. Create a feature branch: `git checkout -b feat/your-feature`
3. Make changes and commit with clear messages
4. Push and open a Pull Request describing your change
- Prefer small, focused changes and include tests where possible.

### License
Add your chosen license (e.g., MIT). Create a LICENSE file in the repository root.

### Notes & Suggestions
- Keep the core logic separated from I/O to simplify testing (e.g., model and service layers vs. CLI).
- Consider adding a simple JSON library (nlohmann/json) if you need JSON persistence.
- For more complex UIs later, consider adding a GUI (Qt) or web front-end with a REST API backend.

---
