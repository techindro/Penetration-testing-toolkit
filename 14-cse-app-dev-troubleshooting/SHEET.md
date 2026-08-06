# 📱 Module 14: Mobile App Development Troubleshooting Guide

Troubleshooting guide for common build errors, Gradle failures, JDK version mismatches, Flutter doctor issues, and emulator bugs across Android Native, Flutter, and React Native.

---

## 🛠️ 1. Gradle Build Failures & JDK Mismatches

### Symptom:
`Unable to find method 'org.gradle.api.tasks.TaskInputs.file'` or `Unsupported Java version`.

### Fix:
1. Match Gradle Version with JDK Version:
   - **Java 17 (LTS):** Gradle 7.3+
   - **Java 21 (LTS):** Gradle 8.5+
2. Set correct JAVA_HOME environment variable:
   ```bash
   export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
   export PATH=$JAVA_HOME/bin:$PATH
   ```
3. Run Clean Build:
   ```bash
   ./gradlew clean --refresh-dependencies
   ```

---

## 🎯 2. Flutter Environment & `flutter doctor` Errors

### Symptom:
`Android license status unknown` or `cmdline-tools component is missing`.

### Fixes:
```bash
# 1. Accept Android Licenses
flutter doctor --android-licenses

# 2. Open Android Studio -> SDK Manager -> SDK Tools tab -> Check "Android SDK Command-line Tools (latest)" -> Apply

# 3. Configure Android SDK Path
flutter config --android-sdk "/path/to/android/sdk"
```

---

## ⚡ 3. Android Emulator & ADB Port Errors

### Symptom:
`adb server version does not match this client` or Emulator stuck on black screen.

### Fixes:
```bash
# Kill and restart ADB daemon
adb kill-server
adb start-server
adb devices

# Fix Emulator HAXM / KVM Hardware Acceleration on Linux
sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils
sudo adduser $USER kvm
```
