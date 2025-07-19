# PSChess
A Chess Engine in PostScript

## PSChess – A Chess Engine in PostScript

See these two articles on seriot.ch:

- [The Making and Inner Working of PSChess](https://seriot.ch/projects/pschess.html)
- [Programming in PostScript](https://seriot.ch/projects/programming_in_postscript.html)

#### Motivation

- To what extend can we execute arbitrary code on a printer?
- How to implement a chess engine in PostScript?
- Can you play chess against your printer?

#### Play in GhostScript

    $ gs -DNOSAFER main.ps

The user plays by entering moves like `d2d4`.
    
Console output:
    
    r...r...        black h8 e8
    pppkb.Q.        320
    ..bqp...
    ...p..Np        P...............
    ...B.Pn.        npp.............
    ..P...PB
    PP.NP..P        -
    ..KR...R        white turn                   

<img src="pschess.png" width="500" align="center"></src>

#### Play on an actual printer

    cat pschess_compact.ps - | nc 172.20.10.2 9100
    
    <enter>
    
    rnbqkbnr             
    pppppppp        0
    ........
    ........        ................
    ........        ................
    ........
    PPPPPPPP        white turn                      
    RNBQKBNR        
    
    >d2d4

#### Limitations

- human plays white, computer plays black
- pawns convert into queens only
