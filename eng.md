![I WILL NOT eat green eggs and ham.][1] 

How many for loops did you write today? This week?<figure class="code"><
figcaption
></figcaption>



| 1
    2
    3
    4
    5
    6 | <span class="line"><span class="kd">var</span> <span
class="nx">i</span><span class="p">;</span
>
    </span><span class="line"><span class="k">for</span><
span class="p">(</span><span class="nx">i</span> <span class="o">=&
lt;/span> <span class="mi">0</span><span class="p">;</span> <span
class="nx">i</span> <span class="o"><</span> <span class="nx">
someArray</span><span class="p">.</span><span class="nx">length</
span><span class="p">;</span> <span class="nx">i</span><span 
class="o">++</span><span class="p">)</span> <span class="p">{</
span
>
    </span><span class="line">  <span class="kd">var</span> &
lt;span class="nx">someThing</span> <span class="o">=</span> <span 
class="nx">someArray</span><span class="p">[</span><span class="nx">
i</span><span class="p">];</span
>
    </span><span class="line">  <span class="nx">doSomeWorkOn&lt
;/span><span class="p">(</span><span class="nx">someThing</span><
span class="p">);</span
>
    </span><span class="line"><span class="p">}</span>
    </span
> |
||</figure>

Sure. That’s harmless enough. Ugly and weird, but not something to really
complain about. But this is all too common:<figure class="code"><figcaption></
figcaption
>



| 1
    2
    3
    4
    5
    6
    7
    8
    9 | <span class="line"><span class="kd">var</span> <span
class="nx">i</span><span class="p">,</span
>
    </span><span class="line">  <span class="nx">j</span><
span class="p">;</span
>
    </span><span class="line"><span class="k">for</span><
span class="p">(</span><span class="nx">i</span> <span class="o">=&
lt;/span> <span class="mi">0</span><span class="p">;</span> <span
class="nx">i</span> <span class="o"><</span> <span class="nx">
someArray</span><span class="p">.</span><span class="nx">length</
span><span class="p">;</span> <span class="nx">i</span><span 
class="o">++</span><span class="p">)</span> <span class="p">{</
span
>
    </span><span class="line">  <span class="kd">var</span> &
lt;span class="nx">someThing</span> <span class="o">=</span> <span 
class="nx">someArray</span><span class="p">[</span><span class="nx">
i</span><span class="p">];</span
>
    </span><span class="line">  <span class="k">for</span><
span class="p">(</span><span class="nx">j</span> <span class="o">=&
lt;/span> <span class="mi">0</span><span class="p">;</span> <span
class="nx">j</span> <span class="o"><</span> <span class="nx">
someThing</span><span class="p">.</span><span class="nx">stuff</
span><span class="p">.</span><span class="nx">length</span><span 
class="p">;</span> <span class="nx">j</span><span class="o">++</
span><span class="p">)</span> <span class="p">{</span
>
    </span><span class="line">      <span class="nx">doSomeWorkOn
</span><span class="p">(</span><span class="nx">someThing</span>&
lt;span class="p">.</span><span class="nx">stuff</span><span class="
p">[</span><span class="nx">j</span><span class="p">]);</span
>
    </span><span class="line">  <span class="p">}</span>
    </
span><span class="line"><span class="p">}</span
>
    </
span
> |
||</figure>

Which on the scale of bad code, isn’t even **that** bad, but you start throwing
some`if`s in there and the insanity really starts.

## I haven’t written a For loop in two years.

“The hell you say?”

It’s true. Cold turkey. Not a single one (ok, you caught me, I just wrote a
couple above), and my code is easier to understand because of my abstinence.

How’d I do it?<figure class="code"><figcaption></figcaption>



| 1
    2
    3 | <span class="line"><span class="nx">_</span><span
class="p">.</span><span class="nx">each</span><span class="p">(</
span><span class="nx">someArray</span><span class="p">,</span> <
span class="kd">function</span><span class="p">(</span><span class="
nx">someThing</span><span class="p">)</span> <span class="p">{</
span
>
    </span><span class="line">  <span class="nx">doSomeWorkOn&lt
;/span><span class="p">(</span><span class="nx">someThing</span><
span class="p">);</span
>
    </span><span class="line"><span class="p">})</span>
    </
span
> |
||</figure>

Or, even better:<figure class="code"><figcaption></figcaption>



| 1 | <span class="line"><span class="nx">_</span><span class="p
">.</span><span class="nx">each</span><span class="p">(</span><
span class="nx">someArray</span><span class="p">,</span> <span class
="nx">doSomeWorkOn</span><span class="p">);</span> <span class="c1
">//thanks paulmcpazzi!</span
>
    </span> |
||</figure>

That’s [underscorejs][2] in action. Clean, easy to read, short, no variables,
stacks of semi-colons… just plain nice.

Here’s another example:<figure class="code"><figcaption></figcaption>



| 1
    2
    3
    4
    5
    6
    7
    8
    9
    10 | <span class="line"><span class="kd">var</span> <span
class="nx">i</span><span class="p">,</span
>
    </span><span class="line">  <span class="nx">result</span
> <span class="o">=</span> <span class="p">[];</span
>
    </span><span class="line"><span class="k">for</span><
span class="p">(</span><span class="nx">i</span> <span class="o">=&
lt;/span> <span class="mi">0</span><span class="p">;</span> <span
class="nx">i</span> <span class="o"><</span> <span class="nx">
someArray</span><span class="p">.</span><span class="nx">length</
span><span class="p">;</span> <span class="nx">i</span><span 
class="o">++</span><span class="p">)</span> <span class="p">{</
span
>
    </span><span class="line">  <span class="kd">var</span> &
lt;span class="nx">someThing</span> <span class="o">=</span> <span 
class="nx">someArray</span><span class="p">[</span><span class="nx">
i</span><span class="p">];</span
>
    </span><span class="line">  <span class="c1">// my hand
already hurts from all this damn typing</span
>
    </span><span class="line">  <span class="k">if</span><
span class="p">(</span><span class="nx">someThing</span><span class
="p">.</span><span class="nx">isAwesome</span> <span class="o">===&
lt;/span> <span class="kc">true</span><span class="p">)</span> <
span class="p">{</span
>
    </span><span class="line">      <span class="nx">result</
span><span class="p">.</span><span class="nx">push</span><span 
class="p">(</span><span class="nx">someArray</span><span class="p
">[</span><span class="nx">i</span><span class="p">]);</span
>
    </span><span class="line">  <span class="p">}</span>
    </
span><span class="line"><span class="p">}</span
>
    </
span
> |
||</figure>

Again, a typical use case for the time honored `for` loop. Meh. Like an ex-
smoker or a recently converted vegan, even the sight of the thing fills me with 
righteous indignation.<figure class="code"><figcaption></figcaption>



| 1
    2
    3 | <span class="line"><span class="kd">var</span> <span
class="nx">result</span> <span class="o">=</span> <span class="nx">_
</span><span class="p">.</span><span class="nx">filter</span><
span class="p">(</span><span class="nx">someArray</span><span class
="p">,</span> <span class="kd">function</span><span class="p">(</
span><span class="nx">someThing</span><span class="p">)</span> <
span class="p">{</span
>
    </span><span class="line">  <span class="k">return</span
> <span class="nx">someThing</span><span class="p">.</span><span 
class="nx">isAwesome</span> <span class="o">===</span> <span class="
kc">true</span><span class="p">;</span
>
    </span><span class="line"><span class="p">})</span>
    </
span
> |
||</figure>

As the underscore method name `filter` suggests, this handy 3 lines of easy to
parse code gives me a new array of**awesome things**.

Or maybe I’d like to do some work on the things and get a new array of the
results?<figure class="code"><figcaption></figcaption>



| 1
    2
    3 | <span class="line"><span class="kd">var</span> <span
class="nx">result</span> <span class="o">=</span> <span class="nx">_
</span><span class="p">.</span><span class="nx">map</span><
span class="p">(</span><span class="nx">someArray</span><span class
="p">,</span> <span class="kd">function</span><span class="p">(</
span><span class="nx">someThing</span><span class="p">)</span> <
span class="p">{</span
>
    </span><span class="line">  <span class="k">return</span
> <span class="nx">trasformTheThing</span><span class="p">(</span>&
lt;span class="nx">someThing</span><span class="p">);</span
>
    </span><span class="line"><span class="p">})</span>
    </
span
> |
||</figure>

Those three functions are insanely useful on a daily basis, and don’t even
scratch the surface of what underscore brings to the table.<figure class="code
"><figcaption></figcaption>



| 1
    2
    3
    4
    5
    6
    7
    8
    9 | <span class="line"><span class="kd">var</span> <span
class="nx">grandTotal</span> <span class="o">=</span> <span class="
mi">0</span><span class="p">,</span
>
    </span><span class="line">  <span class="nx">somePercentage&
lt;/span> <span class="o">=</span> <span class="mf">1.07</span><
span class="p">,</span
>
    </span><span class="line">  <span class="nx">severalNumbers&
lt;/span> <span class="o">=</span> <span class="p">[</span><span 
class="mi">33</span><span class="p">,</span> <span class="mi">54<
/span><span class="p">,</span> <span class="mi">42</span><span 
class="p">],</span
>
    </span><span class="line">  <span class="nx">i</span><
span class="p">;</span> <span class="c1">// don't forget to hoist those 
indices;</span
>
    </span><span class="line"><span class="k">for</span><
span class="p">(</span><span class="nx">i</span> <span class="o">=&
lt;/span> <span class="mi">0</span><span class="p">;</span> <span
class="nx">i</span> <span class="o"><</span> <span class="nx">
severalNumbers</span><span class="p">.</span><span class="nx">length
</span><span class="p">;</span> <span class="nx">i</span><span
class="o">++</span><span class="p">)</span> <span class="p">{</
span
>
    </span><span class="line">  <span class="kd">var</span> &
lt;span class="nx">aNumber</span> <span class="o">=</span> <span 
class="nx">severalNumbers</span><span class="p">[</span><span class
="nx">i</span><span class="p">];</span
>
    </span><span class="line">  <span class="nx">grandTotal</
span> <span class="o">+=</span> <span class="nx">aNumber</span> <
span class="o">*</span> <span class="nx">somePercentage</span><span 
class="p">;</span
>
    </span><span class="line"><span class="p">}</span>
    </span
> |
||</figure>

Oy.<figure class="code"><figcaption></figcaption>



| 1
    2
    3
    4
    5
    6
    7 | <span class="line"><span class="kd">var</span> <span
class="nx">somePercentage</span> <span class="o">=</span> <span 
class="mf">1.07</span><span class="p">,</span
>
    </span><span class="line">  <span class="nx">severalNumbers&
lt;/span> <span class="o">=</span> <span class="p">[</span><span 
class="mi">33</span><span class="p">,</span> <span class="mi">54<
/span><span class="p">,</span> <span class="mi">42</span><span 
class="p">],</span
>
    </span><span class="line">  <span class="nx">grandTotal</
span><span class="p">;</span
>
    </span><span class="line"><span class="nx">grandTotal</
span> <span class="o">=</span> <span class="nx">_</span><span 
class="p">.</span><span class="nx">reduce</span><span class="p">(<
/span><span class="nx">severalNumbers</span><span class="p">,</span
> <span class="kd">function</span><span class="p">(</span><span 
class="nx">runningTotal</span><span class="p">,</span> <span class="
nx">aNumber</span><span class="p">)</span> <span class="p">{</
span
>
    </span><span class="line">  <span class="k">return</span
> <span class="nx">runningTotal</span> <span class="o">+</span> <
span class="p">(</span><span class="nx">aNumber</span> <span class="
o">*</span> <span class="nx">somePercentage</span><span class="p
">);</span
>
    </span><span class="line"><span class="p">},</span> <
span class="mi">0</span><span class="p">)</span
>
    </span> |
||</figure>

It seems a little weird at first, and I **still** hit the docs for methods like
**reduce** above. Knowing they exist, and a flat refusal to use for loops is my
primary weapon. The above methods are really just scratching the surface. The 
underscorejs library is filled with awesome utilities like this that can be 
combined together to create new and wonderful things.

## The 30 day no-loop challenge

Stop.

For the next 30 days, don’t write any for loops. If you see a nasty pile of
those gnarly things, replace them with an**each** or a **map**. Do a little **
reducing**. And let me know how it goes!

Beware. Underscore is the gateway to functional programming. What has been seen
, can’t be unseen. In a good way!

If you’re wanting to dig a little deeper, you should jump over to this
tutorial on[functional programming in javascript][3]. It’s great and only
takes about ½ hour to work through. It is “how the sausage is made” fundamentals
for the underscore functions I used above. Lot’s of wholesome nerd fun!

**note**: *As a more performant alternative to underscore, you might check out
[lodash][4]*

**note**: *it should also be noted that modern browsers support the above
methods natively.`Array.forEach`, `Array.reduce`, and `Array.map` exist, but to
use them you likely need to create shims to fallback for cases when they don’t 
exist. For me, having the consistent underscore (lodash) API is much more 
convenient. YMMV*

**note**: *Yes, for loops **are** faster. I optimize for readability and ease
of use for my team before squeezing performance out of CPUs. I don’t write games,
or rich animated consumer experiences. Big projects, 10s of developers, code 
that already trends towards sprawling and messy.*

The “clean readable code” optimization pays huge dividends, even if it
comes at the cost of (very) marginal performance hits.

Now, if we are doing a big list of items in Angular, we focus on performance in
terms of CPU, but even then, the only time we hit a wall with an unoptimized 
datagrid was on last-gen Android phones.

Clean first! ;)

 [1]: img/no_loops.jpg
 [2]: http://underscorejs.org/
 [3]: http://reactive-extensions.github.io/learnrx/
 [4]: http://lodash.com/benchmarks