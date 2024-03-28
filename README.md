# intel-one-api-hackathon
Tkinter GUI:

Tkinter is a standard GUI (Graphical User Interface) library for Python.
The code sets up a simple GUI application using Tkinter to create the AI-based IT Training System interface.
ITTrainingSystem Class:

The ITTrainingSystem class represents the main functionality of the AI-based IT Training System.
It initializes the GUI elements and handles user interactions.
Text Detection API:

The TextDetector class from the OpenVINO toolkit is imported for text detection purposes. However, in the provided code, text detection functionality is not implemented.
Image Processing API:

The ImageProcessor class from the OpenVINO toolkit is imported for image processing tasks. Similar to text detection, image processing is not utilized in the provided code.
Initialization and Configuration:

The __init__ method initializes the GUI window, sets its title, size, and disables resizing.
A welcome message is displayed using a Label widget.
Two buttons, "Yes" and "No," are provided to start or end the training session, respectively.
Training Start and End:

When the user clicks the "Yes" button, the start_training method is called.
It updates the label to prompt the user to select programming languages.
Three buttons are created dynamically for the user to choose their proficiency level in Python, JavaScript, or Java.
Provide Links:

When the user clicks one of the language buttons, the provide_links method is called.
It checks the selected proficiency level and language against a predefined dictionary of learning links.
If a corresponding link is found, it updates the label with the learning resource link and opens it in the default web browser using webbrowser.open_new_tab().
End Training Session:

If the user clicks the "No" button, the end_training method is called, displaying a farewell message.
The Intel packages, Text Detection API, and Image Processing API, are imported from the OpenVINO toolkit. However, in the provided code, these APIs are not utilized for any specific tasks related to text detection or image processing. They are included for potential future expansion or integration with additional features.
