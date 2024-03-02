# Quantum Network

This is an implementation of a Quantum Network in python using the NetSquid library. The topology of the network is a 
Star topology, this means that the center of the network is a Quantum Source that generates entangled Bell pairs. In 
addition, the points of the star are nodes with quantum memories. <br/> <br/>

![network](https://raw.githubusercontent.com/edoriggio/quantum-network/main/docs/network.png)
*Quantum network topology*
<br/> <br/>

One of the points of the network is a Quantum Repeater. This repeater is connected to a remote node which has a Quantum 
Source as well as a quantum memory. The repeater will receive one qubit from the source, one qubit from the remote node,
and will perform Entanglement Swapping on those qubits. <br/> <br/>

![swapping](https://raw.githubusercontent.com/edoriggio/quantum-network/main/docs/swapping.png)
*Entanglement swapping of Bell pairs*
<br/> <br/>

A more detailed report on the project can be found [here](https://github.com/edoriggio/quantum-network/blob/main/docs/report.pdf).
