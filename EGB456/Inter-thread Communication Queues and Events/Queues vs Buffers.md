|Type|Use|Notes|
|---|---|---|
|Queue|Discrete values, copied, sync, multi|FIFO, safe with ISR|
|Message Buffer|Variable-size messages, no ISR safety|Single writer/reader, callback support|
|Stream Buffer|Continuous bytes, some ISR support|Single writer/reader, not for pointers|