# Authors: Jonathan Chan, Jitesh Nadimpalli
# Credit: Dr. Michael Marsh, Andrew Pachulski

How to run (MAC OS):
1) In terminal, open project folder and type: ruby controller.rb nodes config
1a) Any adjustments to nodes or their ports should be done in the "nodes" file
1b) Any adjustments to the update interval, max payload, or timeout should be done in the "config" file

Commands: given in the form of "COMMAND [args]"

SENDMSG [node] [message]

    Function: send message to node

DUMPTABLE [filename]

    Function: prints current view of the routing table as a CSV to filename
    Format: src, dst, nextHop, distance
    
SHUTDOWN

    Function: shuts down the node and flushes all buffers
    
STATUS

    Function: prints out status information
    Format:
        Name: <node>
        Port: <port the node is listening on>
        Neighbors: <lexicographically sorted list of neighbors>
        
EDGEB [src_ip] [dst_ip] [dst]

    Function: creates symmetric node of cost 1 between nodes at prescribed IP using a single TCP connection
    
EDGEU [dst] [cost]

    Function: updates cost between node to neighbor, non-symmetric
    
EDGED [dst]

    Function: destroys the edge between src node and dst node, non-symmetric
    
SENDMSG [dst] [msg]

    Function: sends msg to dst
    
PING [dst] [num_pings] [delay]

    Function: send num_pings to node with delay seconds in between pings    
    
TRACEROUTE [dst]

    Function: perform a tracerout from src to dst
