# intel-one-api-hackathon
import tkinter as tk
from tkinter.ttk import Label, Button
import webbrowser
from openvino.text_detection import TextDetector  # Intel's Text Detection API
from openvino.image_processing import ImageProcessor  # Intel's Image Processing API

class ITTrainingSystem:
    def __init__(self, master):
        self.master = master
        master.title("AI-based IT Training System")
        master.geometry("400x300")
        master.resizable(False, False)

        self.label = Label(master, text="Welcome to AI-based IT Training System")
        self.label.pack(ipadx=10, ipady=10)

        self.yes_button = Button(master, text="Yes", command=self.start_training)
        self.yes_button.pack(ipadx=10, ipady=5)

        self.no_button = Button(master, text="No", command=self.end_training)
        self.no_button.pack(ipadx=10, ipady=5)

    def start_training(self):
        self.label.config(text="What programming languages are you familiar with?")
        self.beginner_button = Button(self.master, text="Python", command=lambda: self.provide_links('beginner', 'Python'))
        self.beginner_button.pack(ipadx=10, ipady=5)

        self.intermediate_button = Button(self.master, text="JavaScript", command=lambda: self.provide_links('intermediate', 'JavaScript'))
        self.intermediate_button.pack(ipadx=10, ipady=5)

        self.professional_button = Button(self.master, text="Java", command=lambda: self.provide_links('professional', 'Java'))
        self.professional_button.pack(ipadx=10, ipady=5)

    def end_training(self):
        self.label.config(text="Thank you for using AI-based IT Training System")

    def provide_links(self, level, language):
        learning_links = {
            'beginner': {
                'Python': 'https://www.python.org/doc/',
                'JavaScript': 'https://developer.mozilla.org/en-US/docs/Web/JavaScript',
                'Java': 'https://docs.oracle.com/en/java/',
            },
            'intermediate': {
                'Python': 'https://realpython.com/',
                'JavaScript': 'https://www.w3schools.com/js/',
                'Java': 'https://www.tutorialspoint.com/java/index.htm',
            },
            'professional': {
                'Python': 'https://docs.python.org/3/',
                'JavaScript': 'https://developer.mozilla.org/en-US/docs/Web/JavaScript',
                'Java': 'https://docs.oracle.com/en/java/',
            }
        }

        if level in learning_links and language in learning_links[level]:
            link = learning_links[level][language]
            self.label.config(text=f"You can start learning {language} at: {link}")
            webbrowser.open_new_tab(link)
        else:
            self.label.config(text="No learning links available for the selected level and language")

def run_training_system():
    root = tk.Tk()
    it_training_system = ITTrainingSystem(root)
    root.mainloop()

if __name__ == "__main__":
    run_training_system()
