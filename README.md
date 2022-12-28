# Matala1

## Observer Desigh Pattern
##
![alt text](https://upload.wikimedia.org/wikipedia/commons/a/a8/Observer_w_update.svg)

## Interfaces
### Sender
#####
The sender Interface described the Observerable and being implemented by the GroupAdmin Class

### Member
the sender Interface descrbie the Observer and being implemented by the ConcreteMember Class

## Classes

### GroupAdmin
##### 
 * Represents the Observerable part of the "observer desigh pattern".
 * Includes 2 data-members:
 * 1 - UndoableStringBuilder called builder - delegate of UndoableStringBuilder, in order to use its functionality
 * 2 - Set of Members implements by HashSet - The use of HashSet decreases the time complexity of the register and unregister functions, because of the constant use of        contain function that cost only O(1) in HashSet (every register and unregister call the contain function is being used). 
 * The builder make changes on strings, and notify the Members about the changes.

#### UndoAbleStringBuilder
#####
 * The Class of UndoableStringBuilder has 2 data-members:
 * @operations - Stack of Strings, in order to save our last changes, used for undo-function.
 * @sb         - a regular Java StringBuilder, used for StringBuilder methods.

### ConcreteMember
#####
 * Represents the Observer part of the "observer desigh pattern".
 * Includes 2 data-members:
 * 1 - UndoableStringBuilder called usb.
 * 2 - String name - represent the name of the Member.
 * The usb has to be initialized by the sallow copy of the GroupAdmin's UndoAbleStringBuilder, in order
 * to be updated about the whole updates of the UndoableStringBuilder which the member follows.
