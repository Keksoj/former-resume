# hi

Does this work?

```
        UNIX                   UNIX
       SOCKET                 SOCKET
        │ ▲                    │ ▲
        │ │                    │ │
   ┌────▼─┴─────┐         ┌────▼─┴─────┐
   │   client   │         │   client   │       as many more
   │    loop    │         │    loop    │       clients as we
   └─┬───────▲──┘         └──┬─────▲───┘          want
     │       │               │     │
     │       │ mpsc channels │     │
     │       │               │     │
┌────▼───────┴───────────────▼─────┴──────┐
│                                         │
│                 Command                 │
│                  Server                 │
│                                         │
└────┬───────▲───────────────┬─────▲──────┘
     │       │               │     │
     │       │ mpsc channels │     │
     │       │               │     │
   ┌─▼───────┴──┐         ┌──▼─────┴───┐
   │   worker   │         │   worker   │     as many more
   │    loop    │         │    loop    │     workers as we
   └────┬─▲─────┘         └────┬─▲─────┘        want
        │ │                    │ │
        ▼ │                    ▼ │
        UNIX                   UNIX
       SOCKET                 SOCKET
```