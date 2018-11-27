+++
date = "2018-11-26T22:23:08-08:00"
draft = true
tags = []
title = "Typed Array performance in JavaScript"

+++
May 20, 2014 by dave

I was looking at a few JavaScript implementations of [Conway’s Game of Life](http://www.conwaylife.com/wiki/Conway's_Game_of_Life) and I was a little underwhelmed by their performance, so I started wondering how much was related to Array performance in JavaScript.

There’s a better option for arrays of ints: [Typed Arrays](http://www.html5rocks.com/en/tutorials/webgl/typed_arrays/), the smallest object they can store is an 8 bit byte (I only need a boolean), but that’s still a lot less complicated than a full JS object.

Results:  
I tested on Firefox and Chrome on a modern MacBook Pro and an old Windows 7 machine. In every case, typed arrays were faster than plain arrays.

Interestingly, Chrome was slightly faster operating on 32 bit words

On Chrome the typed arrays were \~3x faster, on Firefox they were 25% faster. Somehow Firefox managed to take over 12x as long on my old windows box.

| Browser (Machine) | Int8Array | Int32Array | Array |
| --- | --- | --- | --- |
| Chrome (MacBook Pro) | 216.541ms | 198.340ms | 723.414ms |
| Firefox (MacBook Pro) | 199.7ms | 198.96ms | 252.67ms |
| Chrome (Old Win7) | 668.000ms | 564.000ms | 1878.000ms |
| Firefox (Old Win7) | 7355.06ms | 7163.35ms | 9494.34ms |

To test yourself, you can use [this code](http://jsfiddle.net/eurica/8WESz/) (output goes to the browser console).