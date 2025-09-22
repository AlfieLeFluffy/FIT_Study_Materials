#UI
There are several standard GUI elements that are labelled as **WIMP**:
- **Window** usually represents a running program.
	- **Primary** window of an application (program) usually contains its menu,  and multiple unrelated functions.
	- **Secondary** window usually handles secondary, expansive or additional functionalities. It usually has a fixed aspect, does not have the option to min/maximalizme and is smaller then the primary window. These windows are further divided into:
		- **Modal** windows are dialog inside the frame of the application.
		- **System Modal** windows have priority over the application, such as installation or file choosing dialogue.
		- **Non-modal** windows are non-priority and the user can have them open and still work with the application.
- **Icon** represents a shortcut that lead to some action, such as starting an application, closing it, saving progress, etc.
- **Menu** can be text-based or icon selection, where each option leads to some action.
- **Pointer** is a moving graphical symbol that represents the movement of a physical device such as a mouse, through which the user can select icons or menu elements.
## Additional UI Elements
There are other common UI elements the extend the basic WIMP:
- Buttons
- Toggles
- Labels
- Checkboxes
- Lists
- Sliders
- File Selection
- Input Fields
## Application Window Modes
Application windows can be divided into several modes, each one more complex then the previous one, but also providing extended functionality:
- **Single-Document Interface** (SDI) has one primary windows, several secondary windows and has a straightforward relationship between a window and an object. It is clear, understandable. Each windows has its own menu and there can be multiple instances of the application in the OS bar.
- **Multiple-Document Interface** (MDI) is one application that contains multiple windows. Work with one object can be done through multiple views (multiple open windows) or work can be done on multiple objects in one application window.
- **Tabbed Document Interface** (TDI) is today commonly used paradigm in web browsers, code editors, etc. It is controlled SDI or an SDI with an additional control window, that contains menu, list of open objects (tabs), etc. An additional option is cooperative SDI, where some functions can influence contents of other windows (other tabs).