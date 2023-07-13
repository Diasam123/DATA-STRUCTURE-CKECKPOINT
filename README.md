Problem 1:

To find the sum of all distinct elements from two sets, we can follow these steps:

Create an empty array or set to store the distinct elements.
Iterate over the elements of the first set and add them to the distinct elements array.
Iterate over the elements of the second set and add them to the distinct elements array if they are not already present.
Calculate the sum of all elements in the distinct elements array and return the result.

JAVASCRIPT CODE FOR PROBLEM 1

function sumDistinctElements(set1, set2) {
    const set = [...set1, ...set2];
    let sum = 0;
    for (let i = 0; i < set.length; i++) {
        if (!set1.includes(set[i]) || !set2.includes(set[i])) {
            sum += set[i];
        }
    }
    const distinctElements = [...new Set(set.filter((val) => !set1.includes(val) || !set2.includes(val)))];
    return [sum, distinctElements];
}

const set1 = [3, 1, 7, 9];
const set2 = [2, 4, 1, 9, 3];
const [sum, distinctElements] = sumDistinctElements(set1, set2);
console.log(`Output: ${sum} (distinct elements ${distinctElements})`);

The code above defines a function called sumDistinctElements that takes two sets of elements as input and returns the sum of all distinct elements from the sets and the list of distinct elements. The function first creates a new array that contains all elements from both sets. It then iterates over each element in the array and adds it to the sum if it is not present in both sets. Finally, it returns the sum and the list of distinct elements.


Problem 2:

JAVASCRIPT CODE FOR PROBLEM 2

function dotProduct(v1, v2) {
    let ps = 0;
    for (let i = 0; i < v1.length; i++) {
        ps += v1[i] * v2[i];
    }
    return ps;
}

function isOrthogonal(vectors) {
    for (let i = 0; i < vectors.length; i++) {
        for (let j = i + 1; j < vectors.length; j++) {
            if (dotProduct(vectors[i], vectors[j]) !== 0) {
                return false;
            }
        }
    }
    return true;
}

const vectors = [
    [1, 0],
    [0, -1],
    [3, 4],
    [-4, 3]
];
console.log(`Are the vectors orthogonal? ${isOrthogonal(vectors)}`);

The code above defines two functions. The first function called dotProduct takes two vectors as input and calculates their dot product. The second function called isOrthogonal takes a list of vectors as input and determines whether any two vectors are orthogonal by calling the dotProduct function. If any two vectors have a non-zero dot product, then they are not orthogonal. Otherwise, they are orthogonal.