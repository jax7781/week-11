# week-11
Scripts for week 11
import tkinter as tk

class TaxCalculator(tk.Tk):
    def __init__(self):
        super().__init__()
        self.title("Tax Calculator")

        # Create input fields
        self.gross_income_label = tk.Label(self, text="Gross Income:")
        self.gross_income_entry = tk.Entry(self)
        self.dependents_label = tk.Label(self, text="Dependents:")
        self.dependents_entry = tk.Entry(self)

        # Create compute button
        self.compute_button = tk.Button(self, text="Compute", command=self.calculate_tax)

        # Create output field
        self.total_tax_label = tk.Label(self, text="Total Tax:")
        self.total_tax_output = tk.Label(self)

        # Grid layout
        self.gross_income_label.grid(row=0, column=0, padx=10, pady=10)
        self.gross_income_entry.grid(row=0, column=1, padx=10, pady=10)
        self.dependents_label.grid(row=1, column=0, padx=10, pady=10)
        self.dependents_entry.grid(row=1, column=1, padx=10, pady=10)
        self.compute_button.grid(row=2, column=0, columnspan=2, padx=10, pady=10)
        self.total_tax_label.grid(row=3, column=0, padx=10, pady=10)
        self.total_tax_output.grid(row=3, column=1, padx=10, pady=10)

    def calculate_tax(self):
        # Get input values
        gross_income = float(self.gross_income_entry.get())
        dependents = int(self.dependents_entry.get())

        # Perform tax calculation
        total_tax = gross_income * 0.18 - (dependents * 100)

        # Update output field
        self.total_tax_output.config(text="{:.2f}".format(total_tax))

# Create an instance of the TaxCalculator class
tax_calculator = TaxCalculator()

# Start the main event loop
tax_calculator.mainloop()

import tkinter as tk

class TemperatureConverter(tk.Tk):
    def __init__(self):
        super().__init__()
        self.title("Temperature Converter")

        # Create labels for Fahrenheit and Celsius
        self.fahrenheit_label = tk.Label(self, text="Fahrenheit:")
        self.celsius_label = tk.Label(self, text="Celsius:")

        # Create entry fields for Fahrenheit and Celsius
        self.fahrenheit_entry = tk.Entry(self)
        self.fahrenheit_entry.insert(0, "32.0")  # Set default value for Fahrenheit
        self.celsius_entry = tk.Entry(self)
        self.celsius_entry.insert(0, "0.0")  # Set default value for Celsius

        # Create convert buttons
        self.fahrenheit_to_celsius_button = tk.Button(self, text=">>>>", command=self.convert_fahrenheit_to_celsius)
        self.celsius_to_fahrenheit_button = tk.Button(self, text="<<<<", command=self.convert_celsius_to_fahrenheit)

        # Grid layout
        self.fahrenheit_label.grid(row=0, column=0, padx=10, pady=10)
        self.celsius_label.grid(row=1, column=0, padx=10, pady=10)
        self.fahrenheit_entry.grid(row=0, column=1, padx=10, pady=10)
        self.celsius_entry.grid(row=1, column=1, padx=10, pady=10)
        self.fahrenheit_to_celsius_button.grid(row=2, column=0, padx=10, pady=10)
        self.celsius_to_fahrenheit_button.grid(row=2, column=1, padx=10, pady=10)

    def convert_fahrenheit_to_celsius(self):
        # Get Fahrenheit value
        fahrenheit = float(self.fahrenheit_entry.get())

        # Convert Fahrenheit to Celsius
        celsius = (fahrenheit - 32) * 5 / 9

        # Update Celsius entry field
        self.celsius_entry.delete(0, tk.END)
        self.celsius_entry.insert(0, "{:.2f}".format(celsius))

    def convert_celsius_to_fahrenheit(self):
        # Get Celsius value
        celsius = float(self.celsius_entry.get())

        # Convert Celsius to Fahrenheit
        fahrenheit = celsius * 9 / 5 + 32

        # Update Fahrenheit entry field
        self.fahrenheit_entry.delete(0, tk.END)
        self.fahrenheit_entry.insert(0, "{:.2f}".format(fahrenheit))

# Create an instance of the TemperatureConverter class
temperature_converter = TemperatureConverter()

# Start the main event loop
temperature_converter.mainloop()
