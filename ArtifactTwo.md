# Artifact II
## Enhancement: Algorithms & Data Structure

### Description & Justification
This artifact was originally created for my CS260 course in data structures and algorithms back in 2020. It is comprised of a vector data structure and algorithms used to sort said vector. It is written in C++ coding language and was originally designed to provide functions of loading, displaying, and sorting bids through a quicksort and selection sort. 

This artifact was chosen for inclusion in my eProfile as it specifically covers algorithms and data structure concepts and highlights my understanding of control over external files using these two concepts. It allows me to show the utilization of multiple algorithms to best make use of the data provided and can be translated for use later to showcase work with databases as well. The artifact was improved in multiple ways. Firstly, the style of the code was combed through, and adjustments were implemented to apply consistent indentation and whitespace throughout the code. Comments were added throughout to provide overall description of the .cpp files and the functions they employ as well as making the code transparent and easy to follow with inline comments. Furthermore, the code was made more modular by separating the main function from control functions allowing for the main code to focus on the user interface which could allow for it to be reused for other implementations.
```markdown
  // Display user menu
    int choice = 0;
    while (choice != 9) {
        cout << "Menu:" << endl;
        cout << "  1. Load Bids" << endl; // Calls loadBid function
        cout << "  2. Display All Bids" << endl; // Calls displayBid function
        cout << "  3. Sort By Title" << endl; // Calls titleSort function
        cout << "  4. Sort By ID" << endl; // Calls idSort function
        cout << "  5. Sort By Fund" << endl; // Calls fundSort function
        cout << "  9. Exit" << endl; // Ends program
        cout << "Enter choice: ";
        cin >> choice;
```
Additionally, more functionality was added through more algorithms to allow for the vector to be sorted by additional categories. 
```markdown
void titleSort(vector<Bid>& bids) {
		// index to the current minimum bid
		unsigned int min;

		// pos is the position within the bids that marks sorted/unsorted
		for (unsigned pos = 0; pos < bids.size(); ++pos) {
		min = pos;

			for (unsigned j = pos + 1; j < bids.size(); ++j) {
				if (bids.at(j).title.compare(bids.at(min).title) < 0) {
					min = j;
				}
			}
			if (min != pos) {
				swap(bids.at(pos), bids.at(min));
			}
		}
}
```
```markdown
void idSort(vector<Bid>& bids) {
		// index to the current minimum bid
		unsigned int min;

		// pos is the position within the bids that marks sorted/unsorted
		for (unsigned pos = 0; pos < bids.size(); ++pos) {
			min = pos;

			for (unsigned j = pos + 1; j < bids.size(); ++j) {
				if (bids.at(j).bidId.compare(bids.at(min).bidId) < 0) {
					min = j;
				}
			}
			if (min != pos) {
				swap(bids.at(pos), bids.at(min));
			}
		}
}
```
```markdown
void fundSort(vector<Bid>& bids) {
		// index to the current minimum bid
		unsigned int min;

		// pos is the position within the bids that marks sorted/unsorted
		for (unsigned pos = 0; pos < bids.size(); ++pos) {
			min = pos;

			for (unsigned j = pos + 1; j < bids.size(); ++j) {
				if (bids.at(j).fund.compare(bids.at(min).fund) < 0) {
					min = j;
				}
			}
			if (min != pos) {
				swap(bids.at(pos), bids.at(min));
			}
		}
}
```
This artifact enhancement allowed me to meet the course outcome of designing and evaluating computing solutions that solve a given problem using algorithmic principles and computer science practices/standards appropriate to its' solution through my demonstration of adding additional algorithms for sorting of the vector through multiple categories. The problem was having unsorted data stored in a CSV file and through the data structure of a vector and algorithms we can parse the file, add to a vector, then sort the data in a meaningful way. 

This implementation and enhancement also allowed me to meet the outcome of demonstrating an ability to use well-founded and innovative techniques, skills, and tools in computing practices through the utilization of the Eclipse IDE. I have experience with utilizing Eclipse and Visual Studio, and each offer there own benefits. The use of vectors and sorting algorithms also demonstrates the use of well-founded and innovative techniques. Through my code comments and descriptions, I help to implement and enforce strategies for building collaborative environments that enable diverse audiences to support organizational decision making in the field of computer science by allowing others to better understand and modify/utilize my code. 

### Reflection

Through the process of enhancement of this artifact I learned more about the modularity of C++ code and how a project is made up of different libraries, files, and their included functions. I also learned there is a balance in complexity when coding and formulating a project. Separating code into different functions and files helps keep code cleaner and perhaps easier to understand to a point. But that separation, as more and more functions are added, can become tedious and ultimately make a project more complex than if multiple functions are paired together in one file. This was the challenge I found during this enhancement. Ultimately, I feel like the balance struck between separation of the main function from the rest of the algorithmic functions was the best choice for modularity and complexity and allowed me to incorporate the feedback I received. 

**Repository Link**<br>

[Original Artifact II](https://github.com/Shayden87/CS260) <br>
[Enhanced Artifact II](https://github.com/Shayden87/Algorithms-Data-Structures)

**ePortfolio Links** <br> 

* [Artifact I](ArtifactOne.md)
* [Artifact III](ArtifactThree.md)
* [Code Review](CodeReview.md)
* [Home](index.md)
