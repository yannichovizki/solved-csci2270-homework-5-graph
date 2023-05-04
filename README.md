Download Link: https://assignmentchef.com/product/solved-csci2270-homework-5-graph
<br>
In this assignment, you will implement Dijkstra’s algorithm to find the shortest path between cities.

<strong>G<u>raph Class</u></strong>

Your code should implement graph traversal for cities. A header file that lays out this graph can be found in <strong>Graph.hpp </strong>on Moodle. <em>As usual, do not modify the header file. You may implement helper functions in your .cpp file if you want as long as you don’t add those functions to the Graph class.</em>

Your graph will utilize the following struct:

<table width="640">

 <tbody>

  <tr>

   <td width="640"><strong>struct </strong><strong>vertex</strong>;<strong>struct </strong><strong>adjVertex</strong>{ vertex *v; int weight; };<strong>struct </strong><strong>vertex</strong>{ string name; bool visited; int distance; vertex *pred;vector&lt;adjVertex&gt; adj; };</td>

  </tr>

 </tbody>

</table>

<h2>Tuesday,</h2>







<strong>NOTE (1)</strong>: Coderunner will set <strong>v-&gt;visited = false</strong><strong>; </strong><strong>v-&gt;distance = 0; v-&gt;pred = nullptr; </strong>for all vertices <strong>v </strong>before calling the dijkstraTraverse methods.




<strong>NOTE (2)</strong>: In order to avoid issues with Coderunner for valid traversal sequences, process adjacent nodes in the order that they appear in the adjacency list, i.e., process nodes by going through the adjacency list per node from index 0 to the size of the adjacency list.

<em>We have implemented the following methods for you: </em>

<strong>void addVertex(string name); </strong>

<ul>

 <li>Add new vertex ‘name’ to the graph.</li>

</ul>




<strong>void displayEdges(); </strong>

<ul>

 <li>Display all the edges in the graph.</li>

</ul>




F<u>ormat for printing</u>:




If we create a graph with the following structure




graph.addVertex<strong>(“Boulder”); </strong>graph.addVertex<strong>(“Denver”); </strong>graph.addVertex<strong>(“Las Vegas”);</strong>

<strong> </strong>graph.addEdge<strong>(“Boulder”, “Denver”);</strong> graph.addEdge<strong>(“Las Vegas”, “Denver”);</strong>







We print the edges in the following manner.




<strong>Boulder –&gt; Denver</strong>

<strong>Denver –&gt; Boulder Las Vegas Las Vegas –&gt; Denver</strong>







The order of vertices printed is the same as the order in which they were added to the graph. Similarly, the order of vertices to the right of “–&gt;” sign is the same as the order in which the corresponding edge was added to the graph.

<em> </em>

<strong>void addEdge(string v1, string v2, </strong><strong>int num</strong><strong>); </strong>

➔ Make a connection between v1 and v2 (same as last assignment).<u> <strong>Important</strong></u> point here is to <strong>add weights to the edges</strong>. Each edge will have a corresponding weight attached to it. <em>e.g. </em>addEdge(“Aurora”, “Bloomington”, 5);




<strong>void _grader_setAllVerticesUnvisited(); </strong>

<h2>Tuesday,</h2>

<strong> </strong>

<strong>void _grader_print_shortest_distance(string destination); </strong>

<strong> </strong>

<strong>vertex* searchVertex(string start, vector&lt;vertex*&gt; &amp;vertices) </strong>

<em>You will need to implement the following method:</em> <strong>void dijkstraTraverse(string start); </strong>

Use Dijkstra’s algorithm to compute the single source shortest path in the graph from the start city to all other nodes in its component.




<ul>

 <li>You must use searchVertex() from the source, which has been provided to you within</li>

</ul>

<table>

 <tbody>

  <tr>

   <td width="190"></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

Graph.cpp.




<ul>

 <li><strong>NOTE: </strong>You need to update the <strong>distance </strong>and <strong>pred </strong>attributes for each <strong>v</strong>.</li>

</ul>







<strong>NOTE 1: Do not modify any code provided to you other than dijkstraTraverse(). So, do not change any of the code within Graph.cpp or Graph.hpp. </strong>




<strong>NOTE 2: Once you are done with your assignment in Coderunner, you need to click on ‘Finish attempt’ and the ‘Submit all and finish’. If you don’t do this, your solution will not be graded. </strong>

<strong> E<u>xample Run:</u> </strong>For the given the following Graph and the corresponding adjacency list




<table width="626">

 <tbody>

  <tr>

   <td width="626"><strong>&gt;&gt; Before calling </strong><strong>dijkstraTraverse</strong><strong>(“A”)</strong>

    <table width="608">

     <tbody>

      <tr>

       <td width="76"><strong>Vertex </strong></td>

       <td width="76"><strong>A</strong></td>

       <td width="76"><strong>B</strong></td>

       <td width="76"><strong>C</strong></td>

       <td width="76"><strong>D</strong></td>

       <td width="76"><strong>E</strong></td>

       <td width="76"><strong>F</strong></td>

       <td width="76"><strong>G</strong></td>

      </tr>

      <tr>

       <td width="76"><strong>Distance </strong></td>

       <td width="76"><strong>0</strong></td>

       <td width="76"><strong>0</strong></td>

       <td width="76"><strong>0</strong></td>

       <td width="76"><strong>0</strong></td>

       <td width="76"><strong>0</strong></td>

       <td width="76"><strong>0</strong></td>

       <td width="76"><strong>0</strong></td>

      </tr>

      <tr>

       <td width="76"><strong>Pred </strong></td>

       <td width="76"><strong>NULL</strong></td>

       <td width="76"><strong>NULL</strong></td>

       <td width="76"><strong>NULL</strong></td>

       <td width="76"><strong>NULL</strong></td>

       <td width="76"><strong>NULL</strong></td>

       <td width="76"><strong>NULL</strong></td>

       <td width="76"><strong>NULL</strong></td>

      </tr>

     </tbody>

    </table><strong>&gt;&gt; After calling </strong><strong>dijkstraTraverse</strong><strong>(“A”)</strong>

    <table width="608">

     <tbody>

      <tr>

       <td width="76"><strong>Vertex </strong></td>

       <td width="76"><strong>A</strong></td>

       <td width="76"><strong>B</strong></td>

       <td width="76"><strong>C</strong></td>

       <td width="76"><strong>D</strong></td>

       <td width="76"><strong>E</strong></td>

       <td width="76"><strong>F</strong></td>

       <td width="76"><strong>G</strong></td>

      </tr>

      <tr>

       <td width="76"><strong>Distance </strong></td>

       <td width="76"><strong>0</strong></td>

       <td width="76"><strong>1</strong></td>

       <td width="76"><strong>2</strong></td>

       <td width="76"><strong>3</strong></td>

       <td width="76"><strong>5</strong></td>

       <td width="76"><strong>7</strong></td>

       <td width="76"><strong>4</strong></td>

      </tr>

      <tr>

       <td width="76"><strong>Pred </strong></td>

       <td width="76"><strong>NULL</strong></td>

       <td width="76"><strong>A</strong></td>

       <td width="76"><strong>B</strong></td>

       <td width="76"><strong>B</strong></td>

       <td width="76"><strong>B</strong></td>

       <td width="76"><strong>D</strong></td>

       <td width="76"><strong>B</strong></td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>


