# head-dump

I initially mistook the `head` part of the challenge name to be a clue to look in the `head` tag of the HTML on the page but that was a red-herring.

This task requires you to look through a blog until you stumble upon API documention in Swagger. There is an endpoint that returns diagnostic information about the server. After downloading this large 8mb text file, I started searching for `http` to find an endpoint as the challenge description said we'd need to find a "hidden" endpoint (again another red herring since the dump endpoint was the "hidden" endpoint that I had gotten the file from). After realizing there were 650+ hits for `http`, too many to sift through, I searched instead for `pico`, assuming this "hidden" endpoint would share the domain of the challenge platform. There were 11 results. Lucky for me after iterating the list of results, I actually found the flag file in the dump since it starts with `pico`.

In a perfect world you'd download the dump and then just grep for `picoCTF` and you'd have the flag much quicker than I found it.
