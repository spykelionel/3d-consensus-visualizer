# 3D Consensus Visualizer

A real-time 3D visualization tool for understanding distributed consensus protocols like Raft. Watch nodes change states, messages being sent, and the leader election process unfold in an interactive 3D environment.

![3D Consensus Visualizer](https://img.shields.io/badge/Status-Active-brightgreen)
![Three.js](https://img.shields.io/badge/Three.js-0.150.1-blue)
![License](https://img.shields.io/badge/License-MIT-green)

## 🎯 What is this?

This project creates an interactive 3D visualization of distributed consensus protocols, specifically demonstrating the Raft leader election process. It shows three nodes (A, B, C) as 3D spheres that change color based on their state and display message passing between nodes.

## ✨ Features

- **🎮 Interactive Controls**: Play, pause, step forward/backward, and scrub through timeline
- **🎨 3D Visualization**: Nodes represented as colored spheres with labels
- **📊 Real-time State Display**: See current state of each node
- **📝 Event Log**: Detailed log of all events with descriptions
- **⚡ Adjustable Speed**: Control playback speed (0.5x to 3x)
- **🎯 Step-by-step Debugging**: Move through events one at a time
- **📱 Responsive Design**: Works on different screen sizes

## 🚀 Quick Start

1. **Clone the repository**

   ```bash
   git clone https://github.com/yourusername/3d-consensus-visualizer.git
   cd 3d-consensus-visualizer
   ```

2. **Open in your browser**

   ```bash
   # Simply open index.html in any modern browser
   open index.html
   ```

   Or serve it locally:

   ```bash
   # Using Python
   python -m http.server 8000

   # Using Node.js
   npx serve .

   # Using PHP
   php -S localhost:8000
   ```

3. **Start exploring!**
   - Click **▶️ Play** to start the animation
   - Use the timeline slider to jump to specific times
   - Try the step forward/backward buttons for detailed control

## 💻 System Requirements

- **Browser**: Modern browser with WebGL support (Chrome 60+, Firefox 55+, Safari 12+, Edge 79+)
- **Hardware**: Any device with basic 3D graphics support
- **Network**: No internet required (runs entirely in browser)

## 🌐 Browser Compatibility

| Browser | Version | Status           |
| ------- | ------- | ---------------- |
| Chrome  | 60+     | ✅ Full Support  |
| Firefox | 55+     | ✅ Full Support  |
| Safari  | 12+     | ✅ Full Support  |
| Edge    | 79+     | ✅ Full Support  |
| IE      | Any     | ❌ Not Supported |

## 🎮 How to Use

### Controls Panel (Left Side)

- **▶️ Play/Pause**: Start or stop the animation
- **🔄 Reset**: Return to the beginning
- **⏭️ Step Forward**: Move to the next event
- **⏮️ Step Backward**: Move to the previous event
- **Timeline Slider**: Jump to any specific time
- **Speed Control**: Adjust playback speed (0.5x to 3x)

### Info Panel (Right Side)

- **Current State**: Shows the current state of each node
- **Event Log**: Lists all events with descriptions, highlighting the current one

### Node States

- 🔵 **Blue (Follower)**: Default state, waiting for leader
- 🟡 **Yellow (Candidate)**: Running for leadership
- 🟢 **Green (Leader)**: Elected leader, managing the cluster

## 📖 Understanding the Animation

The visualization shows a typical Raft leader election:

1. **Time 0**: All nodes start as Followers (blue spheres)
2. **Time 2**: Node A sends a vote request to Node B (green line appears)
3. **Time 4**: Node B becomes a Candidate (turns yellow) due to election timeout
4. **Time 6**: Node B requests votes from Node C (green line appears)
5. **Time 8**: Node B becomes the Leader (turns green) after receiving majority votes

## 🛠️ Technical Details

### Built With

- **Three.js 0.150.1**: 3D graphics and rendering
- **Vanilla JavaScript**: No frameworks, pure JS
- **HTML5 Canvas**: WebGL rendering
- **CSS3**: Modern styling and animations

### Architecture

- **Scene Management**: Three.js scene with lighting and shadows
- **Event System**: Timeline-based event processing
- **State Management**: Real-time node state tracking
- **UI Components**: Modular control and info panels

## 🎨 Customization

### Adding New Events

Edit the `trace` array in the JavaScript section:

```javascript
const trace = [
  {
    time: 0,
    event: "start",
    node: "A",
    state: "Follower",
    description: "System starts",
  },
  {
    time: 2,
    event: "send",
    from: "A",
    to: "B",
    type: "RequestVote",
    description: "Vote request",
  },
  // Add your events here...
];
```

### Modifying Node Positions

Change the `nodePositions` object:

```javascript
const nodePositions = {
  A: [-5, 0, 0],
  B: [0, 0, 0],
  C: [5, 0, 0],
  // Add more nodes...
};
```

### Changing Colors

Update the `colors` object:

```javascript
const colors = {
  Follower: 0x9999ff, // Blue
  Candidate: 0xffff99, // Yellow
  Leader: 0x99ff99, // Green
};
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Commit your changes**: `git commit -m 'Add amazing feature'`
4. **Push to the branch**: `git push origin feature/amazing-feature`
5. **Open a Pull Request**

### Ideas for Contributions

- Add support for more consensus protocols (Paxos, PBFT)
- Implement network partition scenarios
- Add sound effects for state changes
- Create more complex node topologies
- Add export/import functionality for custom traces

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Three.js Community**: For the amazing 3D graphics library
- **Raft Paper**: Original consensus algorithm by Diego Ongaro and John Ousterhout
- **Distributed Systems Community**: For inspiration and feedback

## 📞 Support

If you have questions or need help:

- 🐛 **Report bugs**: [Create an issue](https://github.com/yourusername/3d-consensus-visualizer/issues)
- 💡 **Request features**: [Open a feature request](https://github.com/yourusername/3d-consensus-visualizer/issues)
- 📧 **Contact**: [Your email or contact info]

---

**Made with ❤️ for the distributed systems community**

_This tool helps developers and students understand complex consensus protocols through interactive 3D visualization._
