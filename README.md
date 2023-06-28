# 26D-Lattice-DAG-w-Polynomials
26D Lattice DAG w Polynomials

The code begins with including necessary header files: iostream, vector, random, sstream, iomanip, and cwchar. These headers provide functionality for input/output, random number generation, string manipulation, and wide character support.

The code defines a structure LatticeSymbol that represents a lattice symbol with a polynomial. It contains two members: polynomial, which is a vector representing the polynomial coefficients, and complexity, which represents the complexity of the symbol.

The code defines a structure DAGNode representing a node in the Directed Acyclic Graph (DAG) that forms the lattice. It contains two members: parents, a vector of parent indices, and symbol, which is an instance of LatticeSymbol.

The createLattice function takes a vector of integers dimensions as input and returns a vector of DAGNode representing the higher-dimensional lattice with polynomial symbols. This function creates a random number generator and calculates the total number of nodes in the lattice based on the dimensions.

Inside createLattice, the lattice structure is initialized with the correct size using std::vector<DAGNode> lattice(numNodes).

The lattice is filled with random polynomial symbols. For each node in the lattice, a random polynomial of size numCoefficients is generated using a uniform distribution over the range of Unicode code points. The complexity of each symbol is set to a random value between 0 and 99.

The lattice nodes are connected based on adjacency. The function iterates through each node and calculates its corresponding indices in the lattice based on the dimensions. It then finds the neighbors in the positive and negative directions for each dimension and adds their indices to the parents vector of the current node.

The evaluatePolynomial function takes a vector of integers polynomial and a value x as input and evaluates the polynomial at that value using the Horner's method.

The encryptMessage function takes a wide string message and the lattice as input and returns a vector of integers representing the encrypted message. It iterates over each character in the message, finds the corresponding lattice index using the modulus operator, retrieves the polynomial of the lattice node, and evaluates it at the lattice index. The resulting symbol is added to the encrypted data vector.

The decryptMessage function takes a vector of integers encryptedData and the lattice as input and returns the decrypted wide string. It iterates over each symbol in the encrypted data, searches for the lattice node that corresponds to the symbol by evaluating each polynomial at its respective index, and converts the lattice index to an uppercase character, which is then added to the decrypted message.

The intListToString function takes a vector of integers data and converts it to a wide string representation where each integer is formatted with a width of 6 and leading zeros using std::setw and std::setfill. The resulting string is returned.

In the main function, the dimensions of the higher-dimensional lattice are defined. In this case, it's a 26-dimensional lattice with each dimension having 2 elements, resulting in a total of 2^26 nodes.

The createLattice function is called to generate the higher-dimensional lattice with polynomial symbols.

A message is defined as a wide string message containing the text to be encrypted.

The encryptMessage function is called with the message and lattice as input, and the resulting encrypted message is stored in the encryptedMessage vector.
