# Huffman-Coding
## Aim
To implement Huffman coding to compress the data using Python.

## Software Required
1. Anaconda - Python 3.7

## Algorithm:
### Step1: Get the input string
<br>

### Step2:Create tree nodes
<br>

### Step3: Main function to implement huffman coding
<br>

### Step4: calculate frequency of occurence
<br>

### Step5: print the characters and its huffmancode
<br>


## Program:
```
Developed By:SRI SAI PRIYA.S
Register Number:212222240103
```
# Get the input String
```
string = 'DIGITAL IMAGE'
class NodeTree(object):
    def __init__(self, left=None, right=None): 
        self.left = left
        self.right=right
    def children(self):
        return (self.left,self.right)
    def nodes (self):
        return (self.left,self.right)
    def __str__(self):
        return '%s %s' %(self.left,self.right)
```


# Create tree nodes
```
def huffman_code_tree (node, left=True, binString=''):
    if type(node) is str:
        return {node: binString}
    (l, r) = node.children()
    d = dict()
    d.update(huffman_code_tree (l, True, binString + '0'))
    d.update(huffman_code_tree (r, False, binString + '1'))
    return d
```


# Main function to implement huffman coding
```
freq = {}
for c in string:
    if c in freq:
        freq[c] += 1
    else:
        freq[c] = 1
freq = sorted(freq.items(), key=lambda x: x[1], reverse=True)
nodes=freq
```
# Calculate frequency of occurrence
```
while len(nodes)>1:
    (key1,c1)=nodes[-1]
    (key2,c2)=nodes[-2]
    nodes = nodes[:-2]
    node = NodeTree (key1, key2)
    nodes.append((node,c1 + c2))
    nodes = sorted (nodes, key=lambda x: x[1], reverse=True)
```
# Print the characters and its huffmancode
```
huffmanCode=huffman_code_tree(nodes[0][0])
print(' Char | Huffman code ') 
print('----------------------')
for (char, frequency) in freq:
    print('%-4r|%12s'%(char,huffmanCode[char]))
```
## Output:
### Print the characters and its huffmancode

![326174018-cba43a50-d111-482f-9996-73cccbb6d06c](https://github.com/SriSaiPriyaSenthilvel/HUFFMAN--CODING/assets/119475702/68f46e05-c243-475b-9742-202e819863be)

<br>
<br>

## Result
Thus the huffman coding was implemented to compress the data using python programming.
