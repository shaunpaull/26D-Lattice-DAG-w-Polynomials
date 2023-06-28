# 26D-Lattice-DAG-w-Polynomials
26D Lattice DAG w Polynomials

The code begins by including the necessary libraries for input/output operations, working with vectors, generating random numbers, and string manipulation.

Two structs are defined: LatticeSymbol and DAGNode.

LatticeSymbol represents a lattice symbol and consists of two members: polynomial (a vector of integers representing the polynomial coefficients) and complexity (an unsigned integer representing the complexity of the symbol).

DAGNode represents a node in the Directed Acyclic Graph (DAG) structure of the lattice. It contains two members: parents (a vector of integers representing the indices of the parent nodes) and symbol (a LatticeSymbol object representing the lattice symbol associated with the node).

The createLattice function is defined, which takes a vector of integers called dimensions as input. It creates a higher-dimensional lattice with polynomial symbols.

A random number generator is initialized using std::random_device and std::mt19937 (Mersenne Twister engine).

The total number of nodes in the lattice is calculated by multiplying all the dimensions together.

An empty vector called lattice is created to store the lattice nodes.

The lattice vector is filled with random polynomial symbols. For each node, a random coefficient is assigned to each term of the polynomial, and a random complexity value between 0 and 99 is assigned to the symbol.

The lattice nodes are connected based on adjacency. For each node, the indices of its neighbors in the positive and negative directions are calculated, and if the indices are within the valid range, they are added as parents of the current node.

The evaluatePolynomial function is defined, which takes a vector of coefficients (polynomial) and a value (value) as input. It evaluates the polynomial represented by the coefficients at the given value and returns the result.

The encryptMessage function is defined, which takes a string (message) and the lattice as input. It encrypts the message using the higher-dimensional lattice symbols.

For each character in the message, the corresponding lattice index is obtained by taking the modulo of the character with the size of the lattice.

The polynomial coefficients associated with the lattice symbol at the obtained index are retrieved.

The lattice index is used as the value to evaluate the polynomial, resulting in the encrypted symbol.

The encrypted symbols are stored in a vector called encryptedData.

The decryptMessage function is defined, which takes the encrypted data (a vector of integers) and the lattice as input. It decrypts the message using the higher-dimensional lattice symbols.

For each encrypted symbol, the corresponding lattice index is determined by searching for the lattice index where the evaluated symbol matches the encrypted symbol.

The lattice index is converted to a character by taking the modulo of the index with 256.

The decrypted characters are concatenated to form the decrypted message.

The intListToString function is defined, which takes a vector of integers (data) and converts it to a string representation.

The main function is implemented.

The dimensions of the higher-dimensional lattice are defined as a vector of integers. In this example, a 26-dimensional lattice with each dimension set to 2 is used.

The createLattice function is called to generate the higher-dimensional lattice with polynomial symbols.

A message is defined as a string.

The encryptMessage
