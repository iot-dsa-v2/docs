The status codes in the range from 00 to 0F correspond to the codes from 80 to FF. The 00-0F range is used for conditions that permit the stream to remain open, while 80-FF means the stream must be closed. 


| Code(hex) | Message  | Remarks |
|:-------------:| ------------- |  ------------- | 
| 00     | OK | Still streaming |
| 01     | Initializing | The current value is valid, but there is more data to come before current values can be fully usable  |
| 0E| Not available| Might be disconnected and in the process of subscribing, usually for subscribe and list response|
| 10     | Dropped | Some messages are dropped in the queue |
| 20 | Closed | Closed normally, with no error  |
| 2E| Disconnected | Stream must be closed, usually for invoke response |
| 40| Permission denied|
| 41| Not supported|
| 44| Invalid message| Protocol level|
| 45| Invalid parameter| Action level |
| 48| Busy| Client cannot accept additional requests|
| 50| Internal Error | Responder code has a internal error, check the `Error Detail` header for more information. |
| 61 | Alias loop| The number of aliased routings for this request has exceeded the maximum allowed. 
| C9 | Connection error, Incorrect auth value| 
| F0 ~ FF | Reserved| Should never be sent to the network. So it is safe to use these code for internal status that's not related to protocl| 
