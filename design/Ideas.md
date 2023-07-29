# High-level idea

## Concepts

- Nodes have inputs and outputs.
- Nodes can be connected together by the user - outputs can be connected to inputs.
- There are different types of inputs and outputs:
  - Audio
  - MIDI
  - CV (Control Voltage)
- The node determines how many channels it has for each type of input/output.
  - E.g. a node might expose 2 audio input channels, 1 MIDI channel and 8 CV channels, with just 2 audio output channels.
- Nodes can be a container for different things:
  - VST plugin
  - Device (e.g. hardware) input/output
    - Note that device inputs should appear as outputs in the system and vice versa.
    - Maybe implement VST plugins to represent this so that all nodes can be the same?
- Hide the concept of filepaths from the graph.
  - Have a "plugin resolver", so plugins can be referred to by name/ID.
    - Maybe use a combination of developer name and plugin name?
- Should be able to export/import the graph.  Maybe export as JSON?
  - When importing, if a plugin cannot be found (e.g. not installed on the device), allow the user to select another to take its place.

## GUI

### Views

- Visualize the nodes in a graph - be able to edit the connections.
- Show a VST plugin's GUI.

Layout ideas:

1. Full screen graph.  When the user selects a node, display a button to show the node's GUI full-screen.
2. Split-screen:
    - One part to show the graph.
    - One part to show the GUI for the selected node.
