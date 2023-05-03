Download Link: https://assignmentchef.com/product/solved-cs161-problem4
<br>



<ol>

 <li><strong> </strong>Suppose that <em>h </em>: <em>U </em>→ {0<em>,…,n</em>−1} is a uniformly random function. That is, <em>h</em>(<em>i</em>) is distributed uniformly at random in the set {0<em>,…,n </em>− 1} for all <em>i</em>, and <em>h</em>(<em>i</em>) are independent for all <em>i</em>. Prove that for any <em>x </em>6= <em>y </em>∈ <em>U</em>,</li>

</ol>

<strong>[We are expecting: A short but rigorous proof.]</strong>

<ol start="2">

 <li><strong> </strong>This exercise references the IPython notebook ipynb as well as the files mysteryA.pickle and mysteryB.pickle.</li>

</ol>

In the IPython notebook, run the cells to load the hash families <em>A </em>and <em>B</em>. Both <em>A </em>and <em>B </em>are lists of functions <em>h </em>: {0<em>,…,</em>21} → {0<em>,</em>1<em>,</em>2}. As shown in the notebook, at first glance both of these seem like reasonable hash families. <strong>However, </strong>one of them is a universal hash family and one of them is not. Which one is which? Play around with both hash families in Python until you figure it out.

<strong>[We are expecting: Your answer, along with compelling numerical evidence (either numbers or a plot), and an explanation about why your numerical evidence is compelling and what it has to do with the definition of a universal hash family.]</strong>

<h1>Problems</h1>

You may talk with your fellow CS161-ers about the problems. However:

<ul>

 <li>Try the problems on your own <em>before </em></li>

 <li>Write up your answers yourself, in your own words. You should never share your typed-up solutions with your collaborators.</li>

 <li>If you collaborated, list the names of the students you collaborated with at the beginning of each problem.</li>

</ul>

<ol>

 <li><strong> </strong>Your friend has a proposal for a new universal hash function <em>h </em>: U → {0<em>,…,n </em>− 1}, where U = {0<em>,…,n</em><sup>2</sup>−1}. Your friend thinks that you can skip this whole “choose uniformly from a universal hash family” stuff, and just go with</li>

</ol>

<em>h</em>(<em>x</em>) = <em>x </em>mod <em>n.</em>

More precisely, your friend says, just take the hash family H = {<em>h</em>} to be the set with just this one function in it.

(a) <strong> </strong>Your friend doesn’t have a very good track record on these homework sets, so you are dubious even before you hear their argument. Prove to your friend that their choice does <em>not </em>satisfy the key property of a universal hash family.

<strong>[We are expecting: A rigorous proof, using the definition of a universal hash family.] </strong>(b) <strong>(1 pt.) </strong>Even given your proof, your friend plows on. Their first point:

Let <em>h </em>= <em>x </em>mod <em>n </em>be as above. If we choose <em>x </em>6= <em>y </em>uniformly at random<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> from U, then , where the probability is over the random choice of <em>x </em>and <em>y</em>.

Do you agree?

<strong>[We are expecting: Whether the statement is true or false, and a convincing argument either way.]</strong>

(c) <strong> </strong>Your friend continues:

Given the computation above, we have

<em>.</em>

This is the definition of a universal hash family, so {<em>h</em>} must be a universal hash family.

Do you agree?

<strong>[We are expecting: Whether this conclusion correctly follows from the statement in part (b), and a convincing argument either way.]</strong>

<ol start="2">

 <li><strong> </strong>Let <em>T </em>be a Red-Black tree with root <em>x</em>. Let <em>T<sub>L </sub></em>be the subtree rooted at <em>x</em>’s left child, and let <em>T<sub>R </sub></em>be the subtree rooted at <em>x</em>’s right child.</li>

</ol>

Decide if each of the following statements are true or false. If it is true, give a proof. If it is false, give a counter-example.

<ul>

 <li><strong> </strong>In the set-up above, we must have</li>

</ul>

1          and         <em>,                                               </em>(1)

where |<em>T</em>| denotes the number of nodes in <em>T </em>(including the root, not including NIL nodes).

<ul>

 <li><strong> </strong>In the set-up above, we must have</li>

</ul>

1          and         <em>,                                           </em>(2)

where |<em>T</em>| denotes the number of nodes in <em>T </em>(including the root, not including NIL nodes).

<strong>[We are expecting: For each, either a rigorous proof, or an explicit counter-example.]</strong>

<strong>[HINT: You may use a claim that we proved in class.]</strong>

<ol start="3">

 <li>A large flock of <em>T </em>Colorful Geese will migrate south for the winter over the Gates building in the next few weeks. Colorful Geese are an interesting species. They can come in a huge number of colors—say, <em>M </em>colors—but each flock only has <em>m </em>colors represented, where <em>m &lt; T</em>. You’d like to be able to answer queries about what colors of geese appeared in the flock. The birds will fly overhead one at a time, and after they have flown by they won’t come back again.</li>

</ol>

For example, if <em>T </em>= 7, <em>M </em>= 100000 and <em>m </em>= 3, then a flock of <em>T </em>colorful geese might look like:

seabreeze, seabreeze, brick red, ultraviolet, brick red, ultraviolet, seabreeze

You’ll see this sequence in order, and only once. After the birds have gone, you’ll be asked questions like “How many brick red geese were there?” (Answer: 2), or “How many neon orange geese were there?” (Answer: 0).

You have access to a universal hash family H, so that each function <em>h </em>∈ H maps the set of <em>M </em>colors into the set {0<em>,…,n </em>− 1}. For example, one function <em>h </em>∈ H might have <em>h</em>(seabreeze) = 3.

<ul>

 <li><strong> </strong>Suppose that <em>n </em>= 10<em>m</em>, and you only have space to store <em>n </em>numbers in the set {0<em>,…,T</em>}, as well as one function <em>h </em>from H. Use the universal hash family H to create a randomized data structure that fits in this space and that supports the following operations:

  <ul>

   <li>Update(color): Update the data structure when you see a goose with color color.</li>

   <li>Query(color): Return the number of geese of color color that you have seen so far. For each query, your query should be correct with probability at least 9/10. That is, for all colors <em>i</em>,</li>

  </ul></li>

</ul>

P{Query(<em>i</em>) = the number of geese with color<em>.</em>

You want each of these operations to be done in <em>O</em>(1) time (in the worst case), assuming that you can evaluate a function <em>h </em>∈ H in <em>O</em>(1) time.

<strong>[We are expecting: An explanation of how you will implement your operations, and a short but rigorous proof that your operations meet the requirements.]</strong>

<ul>

 <li><strong> </strong>Suppose that you now have ten times the space you had in part (a). Adapt your data structure from part (a) so that the Query operation is correct with probability 1 .</li>

</ul>

<strong>[We are expecting: An explanation of how you will implement your operations, and a short but rigorous proof that your operations meet the requirements.]</strong>

<a href="#_ftnref1" name="_ftn1">[1]</a> That is, choose <em>x </em>uniformly at random from U and then choose <em>y </em>uniformly at random from U{<em>x</em>}