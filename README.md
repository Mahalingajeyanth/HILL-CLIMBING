<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name:MAHALINGA JEYANTH V       </h3>
<h3>Register Number: 212224220057           </h3>
<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
  <ul>
<li>if it is a goal state, then return it and quit</li>
<li>if it is not a goal state but better than current state then make new state as current state</li>
<li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

</p>
<hr>
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

<hr>
<h2>Sample Input and Output</h2>
<h2>Sample String:</h2> Artificial Intelligence
<h2>Output:</h2>
Score: 643  Solution :  8RzF:oG ]%;CPORRMe!zGvk<br>
Score: 609  Solution :  8RzF:oG ]%;CPqRRMe!zGvk<br>
Score: 604  Solution :  8RzF:oG ]%;CPqRRMe!zGqk<br>
Score: 594  Solution :  8RzF:oG ]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
....................................................<br>
..................................................<br>
................................................<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 0  Solution :  Artificial Intelligence<br>

<H3>PROGRAM</H3>

<pre><code>

import random
import string

def random_string(length):
    chars = string.ascii_letters + string.punctuation + " "
    return ''.join(random.choice(chars) for _ in range(length))

def fitness(target, candidate):
    return sum(1 for t, c in zip(target, candidate) if t != c)

def mutate(candidate):
    chars = string.ascii_letters + string.punctuation + " "
    i = random.randint(0, len(candidate) - 1)
    new_char = random.choice(chars)
    candidate = list(candidate)
    candidate[i] = new_char
    return ''.join(candidate)

target = "Artificial Intelligence"
current = random_string(len(target))
score = fitness(target, current)
iteration = 0

print(f"Target String: {target}\n")

while score > 0:
    iteration += 1
    candidate = mutate(current)
    candidate_score = fitness(target, candidate)
    if candidate_score < score:
        current = candidate
        score = candidate_score
        print(f"Iteration {iteration}: Score: {score} Solution: {current}")
</code></pre>

<h3>OUTPUT</h3>

<img width="714" height="829" alt="image" src="https://github.com/user-attachments/assets/5737b9ed-6f0e-4d5d-9606-90c9b5ffe3b5" />

<h3>RESULT</h3>

<P>Thus,to Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration is executed successfully. </P>
