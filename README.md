# motivation
an upcoming rework of a project is expected to be running against at least 1000 users at the same time. the current version of the project uses python + fastapi. so far, both have satisfied our requirements; being a straight up simple http server.

but now we're looking for possible new approaches (languages and their ecosystems) so that we can be prepared on handling numerous requests. some of these languages have nice error messages, which is always welcomed. 

so i have chosen to benchmark the following languages for the rework:
1. CPython
2. C#
3. Gleam
4. Golang

although i am a fan of rust, it unfortunately isn't simple enough to be considered an option as of now.

# benchmark
each language will have a tcp listener setup with their own respective standard library. there will be a client and a dummy third party. the dummy listener will only take a tcp request and respond with the same data, just to keep it simple and see how fast can a language's tcp client craft a request and send.

there are 4 types of requests (forward, sum, array processing, object processing). types may stack.
1. forward: forwards to dummy
2. sum: sum the numbers
3. array processing: processes array
4. object processing: processes object or struct, preferably struct

the test client will randomly generate N amount of request data first before starting.

# folders
- client: client script
- dummy: dummy server listener
- pyc, cs, glm, go: respective listener folders

# note
readme will be updated again. what are stated here aren't final.
