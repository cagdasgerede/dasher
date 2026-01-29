# Expat XML Parser Integration

This project uses vcpkg to provide the Expat XML parser as a static library, eliminating the need for external DLL dependencies.

## Setup (One-time)

1. **Install vcpkg:**
   ```bash
   git clone https://github.com/Microsoft/vcpkg.git C:\vcpkg
   cd C:\vcpkg
   bootstrap-vcpkg.bat
   ```

2. **Install Expat:**
   ```bash
   vcpkg install expat:x86-windows-static
   ```

3. **Integrate with Visual Studio:**
   ```bash
   vcpkg integrate install
   ```

## Project Configuration

- **Library:** `C:\vcpkg\installed\x86-windows-static\lib\libexpatMT.lib`
- **Headers:** `C:\vcpkg\installed\x86-windows-static\include`
- **Preprocessor:** `XML_STATIC` (for static linking)

## Result

- Dasher.exe runs without requiring `libexpat.dll`
- Expat is statically linked into the executable
- No external dependencies for XML parsing

## Troubleshooting

If build fails:
1. Ensure vcpkg is installed at `C:\vcpkg`
2. Run `vcpkg install expat:x86-windows-static`
3. Verify the library exists at the path above
