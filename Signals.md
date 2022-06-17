# Signals

This document aims at explaining how signals work.

## No signals

Without using signals, you can only have a single train navigating your network:

![image](./Images/no_signals.gif)

## Normal signals

The normal signals allows you to divide a network in "blocks". Each block can only be occupied by a single train.

### Separating a loop in blocks

With this principle, we can place signals along the tracks to make different blocks, thus allowing more trains to navigate the network at once:

![image](./Images/3_signals.gif)

Notice how the trains slow down when approaching a red signal. A red signal means the train will stop at it. An orange signal means the block is reserved by a train.

Here is a better illustration of a train stopping at a red signal:

![Image](./Images/signals_stops.gif)

### Limitations

As you can see, the circuit has been laid out with two tracks on one side. The goal is to allow a train to overtake another if one track is occupied. This can be useful for stations for example.

Here is what happens with the current setup, using only normal signals:

![Image](./Images/signal_stops_wrong_path.gif)

Can you spot the problem? The train tries to enter the segment that is currently occupied and then waits at the red signal at the entrance of the first overpass track. Let's see how we can improve this using chains signal.

## Chain signals

Chains signals will repeat the signal that is in front of them. This is usually usefull when one block has multiple exits. This is the cas for the block leading into the two overpass blocks:
- It has a single entrance
- It has two possible exits

### Alternate paths

By simply changing the signal at the entrance of the block with a chain signal, we can see a different behavior:

![image](./Images/chain_signal_overpass.gif)

The train now chooses the alternate path to get to his destination directly! Let's see what happens when we have more trains:

![image](./Images/chain_signal_overpass_3_trains.gif)

The train was waiting before entering the two parallel lines, and chose his path once one of the two lines got freed. This is what is usually used to create stations in loops.