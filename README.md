# Data_Bus_Conversion
The data bus converter is designed to convert a N-bit wide data input into 8-bit wide outputs.
The converter operates based on valid signals: Example: An input_valid signal that indicates when the 24-bit data is available and an output_valid signal that is asserted for three clock cycles to ensure that all three 8-bit segments of the data are output sequentially.

# Functional Description:
Input Signals:
clk: Clock signal.
rst: Reset signal (active high), which resets the internal state.
input_data: 24-bit wide data input.
input_valid: Signal indicating that input_data is valid for processing. This signal is high for a single clock cycle.

Output Signals:
output_data: 8-bit wide data output.
output_valid: Signal indicating that output_data is valid. This signal is high for three clock cycles, each corresponding to a different 8-bit segment of the 24-bit input data.

# Operational Flow:
Data Latching:
When input_valid is asserted (high), the 24-bit input data is latched into a temporary register.

Sequential Data Output:
The latched 24-bit data is divided into three 8-bit segments.
The output_valid signal is asserted for three consecutive clock cycles, with each cycle corresponding to the output of one 8-bit segment:
In the first cycle, the least significant 8 bits are output.
In the second cycle, the middle 8 bits are output.
In the third cycle, the nost significant 8 bits are output.

Reset Operation:
If the rst signal is asserted, the internal state machine and any temporary storage registers are reset to their initial states.

# Simulation Result:
![image](https://github.com/user-attachments/assets/8eb354ef-877b-40ff-8c1a-7b0f795c21f6)
