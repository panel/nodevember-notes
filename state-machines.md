# Driven! Events, State Machines and Node
Beat Zenerino

## Reactive Systems
Reactive System continuously interact with its environment, using inputs and outputs that are either continuous in time or discrete. The inputs and outputs are often async.

## Example: Vending Machine
- inputs
 - insert coin
 - make selection
 - cancel
- outputs
 - soda
 - message
- states
 - Idle
 - Count Coins
 - Dispense
 - Give Change

## State Transition Diagram
Nodes are states and directional edges are actions. Must have an initial state.

### Transitions
3 parts: event[guard]/behavior

## FSM in UI Design
- [David Kourshid, "Infinitely Better UIs with Finite Automata"](https://www.youtube.com/watch?v=VU1NKX6Qkxc)
- [Ryan Florence, "Rambling thoughts on React and Finite State Machines"](https://www.youtube.com/watch?v=MkdV2-U16tc)
- ["Using Finite State Machines in Baxi's Booking System"](https://blog.baxi.taxi/using-finite-state-machines-in-baxis-ride-booking-system-126c52952a04)
