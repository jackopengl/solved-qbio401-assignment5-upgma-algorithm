Download Link: https://assignmentchef.com/product/solved-qbio401-assignment5-upgma-algorithm
<br>
We are going to write a UPGMA algorithm in Python and analyze some human data.

On Blackboard, you can find a file named upgmaData.py, which contains:

<ol>

 <li><em>humansList</em> (and <em>testList</em>) are species lists. They are in the form of a tuple.</li>

 <li><em>humansDistances</em> (and <em>testDistances</em>) are dictionaries specifying pairwise distances between species. They are in the form where the key is a tuple which is a pair of species name, e.g., (“species A”,”species B”) and the value is the pairwise distance. The following are the details for the human data:</li>

</ol>

Modern human data: distances based on mitochondrial sequence

<table width="623">

 <tbody>

  <tr>

   <td width="216">San</td>

   <td width="408">San individual from southern Africa</td>

  </tr>

  <tr>

   <td width="216">Yoruba</td>

   <td width="408">Yoruba individual from western Africa</td>

  </tr>

  <tr>

   <td width="216">Finnish</td>

   <td width="408">Finnish individual from northern Europe</td>

  </tr>

  <tr>

   <td width="216">Kikuyu</td>

   <td width="408">Kikuyu individual from eastern Africa</td>

  </tr>

  <tr>

   <td width="216">Papuan</td>

   <td width="408">Papuan individual from New Guinea</td>

  </tr>

  <tr>

   <td width="216">Han</td>

   <td width="408">Han individual from China</td>

  </tr>

 </tbody>

</table>




Note: use “<em>from upgmaData import *</em>” on the first line of your code to be able to use the data.




Write the following Python <em>class</em> for a tree node (as taught in Jinsen’s discussion):

<h1>1.       TreeNode</h1>

Has four properties including <em>key</em>, <em>distance</em>, <em>left</em> and <em>right</em>, where <em>key</em> is for storing species name, <em>distance</em> is for branch length, <em>left</em> is for the left child and <em>right</em> is for the right child. The class has a function <em>print</em> to print the tree structure in the form of (<em>key</em>, <em>distance</em>, <em>left</em>, <em>right</em>). For example, (‘W_X’,0.5,(‘W’,0,(),()),(‘X’,0,(),())) is for the tree W_X with left child (‘W’,0,(),()) and right child (‘X’,0,(),()); the branch length to its child is 0.5.




Write the following functions:

<h1>2.       findClosestPair(Distances)</h1>

Inputs <em>Distances</em> dictionary and returns the key for the pair of nodes that are closest. For example, if the input is <em>testDistances</em>, the function returns <em>(‘W’, ‘X’)</em>.




<h1>3.       updateDist(Distances, newNode)</h1>

Inputs <em>Distances</em> dictionary and a new tree node. Updates the <em>Distances</em> dictionary by adding the distances between <em>newNode</em> and all the other nodes. Does not calculate the distance between <em>newNode</em> and its children in the <em>Distances</em>. This function returns the updated <em>Distances</em> dictionary.




<h1>4.       upgma(Distances)</h1>

This function runs the UPGMA algorithm described in lecture. First, it initializes a list <em>TreeNodesList</em> with multiple new <em>TreeNode</em> referring to <em>humansList </em>(the list <em>TreeNodesList</em> should contain six <em>TreeNodes</em>). Then, it repeats the following steps until there is only one tree node left in the list <em>TreeNodesList</em>, at which point this tree is returned.

<ol>

 <li>Find the key for the closest pair of nodes in <em>Distances</em> (use <em>findClosestPair</em>)</li>

 <li>Create a new <em>TreeNode</em> and assign the pair of nodes stored in <em>TreeNodesList</em> as its children. Calculate the distance between the new <em>TreeNode</em> to its children and store the value in the new <em>TreeNode</em>.</li>

 <li>Update the <em>TreeNodesList</em> by removing the pair of nodes referring to a.</li>

 <li>Update the <em>Distances</em> dictionary (use <em>updateDist</em>)</li>

 <li>Add the new <em>TreeNode</em> into <em>TreeNodesList</em>.</li>

</ol>




Use aforementioned functions to analyze human data:

<ol start="5">

 <li>Use <em>upgma</em> to generate one tree using <em>humansList</em> and <em>humansDistances</em>. Turn in your code, the output the code for humans, and explain what you find from the results</li>

</ol>














