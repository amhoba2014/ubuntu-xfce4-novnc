# Ubuntu 20.04 Docker Container with XFCE Desktop over VNC / noVNC

Are you looking for a fully-fledged Ubuntu Docker container with a complete desktop experience? This Docker image provides quick access to an entire Ubuntu Desktop (XFCE) directly from within the container. It utilizes `tightvncserver` for VNC connections and `noVNC` for easy browser access.

> **IMPORTANT:** This image is intended for testing purposes only. It is not recommended for production systems or any productive uses. Feel free to modify it as needed; build instructions are provided below.

## Features
- Full XFCE desktop environment
- Access via VNC and noVNC (browser-based)
- Customizable settings for display resolution and VNC password

## Build & Install

1. **Clone the repository:**

```bash
git clone https://github.com/amhoba2014/ubuntu-xfce4-novnc && cd ubuntu-xfce4-novnc
```

2. **Build the Docker image:**

```bash
docker build -t ubuntu-xfce4-novnc .
```

- **Optional Arguments:**
  - `--build-arg VNCPWD=changeme`: Set a password for VNC access (default: `changeme`).
  - `--build-arg VNCDISPLAY=1920x1080`: Set the display resolution for the VNC server (default: `1920x1080`).
  - `--build-arg VNCDEPTH=16`: Set the display depth for the VNC server (default: `16`).

3. **Run the container:**

```bash
docker run -it -p 9876:9090 --name ubuntu-container ubuntu-docker
```

Replace `9876` with a any port on your host system if you will.

4. **Access the desktop:**
Open your browser and navigate to:

```bash
https://YOUR_PUBLIC_OR_LOCAL_IP:9876/vnc.html
```

5. **Certificate Verification:**
If a certificate warning appears, verify the SHA256 certificate fingerprint shown in the command prompt when starting the container.

6. **Password Entry:**
If prompted for a password, enter either the default password (`changeme`) or the custom password you set during the build process.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues to discuss improvements or features.
