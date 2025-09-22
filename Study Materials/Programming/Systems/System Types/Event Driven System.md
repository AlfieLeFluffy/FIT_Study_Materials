#System
Event driven systems are system that specialize in detection, processing and reaction to events. The application flow is driven by events, such as peripheral input. The program listens to these events and then reacts to them. In [[Hardware (HW)]] this is done through [[Interrupt]]s, which is highly utilized. Systems made in this style are running an infinite loop and await an incoming event, or they themselves are checking if an input isn't toggled ([[Polling]]), or it uses a message system. Examples of such system are:
- QT: signals and slots
- callbacks