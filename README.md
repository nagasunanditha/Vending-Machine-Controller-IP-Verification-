# Vending-Machine-Controller-IP-Verification-
## Project Overview
This repository contains the *UVM-based verification environment* for the *Vending Machine Controller (VMC)* IP.  
The DUT implements a configurable vending machine controller supporting multiple items, currencies, and operational modes.

## Objectives
- Verify reset, configuration, and operational states  
- Validate APB-based register interface operations  
- Ensure correct dispense logic and change calculation  
- Check error scenarios (invalid item, underpayment, out-of-stock)  
- Achieve Coverage

## Verification Environment
- *Methodology:* UVM (Universal Verification Methodology)  
- *Language:* SystemVerilog  
- *Agents Used:*  
  - cfg_agent → APB configuration  
  - currency_agent → Currency input  
  - item_agent → Item selection  
  - dispense_agent → Output monitoring  
- *Scoreboard & Checkers* for functional correctness  
- *Assertions* for FSM and protocol compliance  

## Test Categories
- *Reset Tests*  
- *Configuration Tests* (APB read/write, edge cases)  
- *Operation Tests* (exact pay, overpay, underpay, multi-currency, stock check)  
- *Error Handling Tests* (invalid item, unsupported currency)  
- *Randomized & Stress Tests*  
- *Timing Tests* (latency ≤10 cycles, single output per transaction)  


## Bugs Identified
- pready signal declared but unused in DUT  
- Missing synchronization for asynchronous currency clock domain  
- FSM misbehavior when currency inserted during cfg_mode  
- Multiple dispense pulses observed in stress scenarios  


## Reference
Full code and testbench are available here on *EDA Playground*:  
[Run on EDA Playground](https://edaplayground.com/x/w234)
