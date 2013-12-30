buster
======

The fuzzing is done at 3 levels: field, message (payloads) and state machine.

The operations are: in_list (sets the value of a field to other values), near_value (decreases/increases numerical fields), payload_multiply (inserts multiple payloads of the same type or deletes it), payload_scramble (random payload order), del_from_field (deletes field(s)), payload_insert (inserts an unexpected payload), replace_bytes_random_pos (inserts character(s) inside field). 

FSM fuzzing inserts Delete/Notify informational messages between IKE_SA_INIT and IKE_AUTH exchanges, before and after. 
The fuzzer also uses some manually crafted packets for other fuzzing ideas. 

There is a Target Manager that detects crashes and messages that caused them and provides synchronization, resets target configuration and so on. 

It starts with punch.py
