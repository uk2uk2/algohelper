import sys

class bcolors:
    HEADER = '\033[95m'
    OKBLUE = '\033[94m'
    OKCYAN = '\033[36m'
    OKYELLOW = '\033[33m'
    OKGREEN = '\033[92m'
    WARNING = '\033[93m'
    FAIL = '\033[91m'
    ENDC = '\033[0m'
    BOLD = '\033[1m'
    UNDERLINE = '\033[4m'
    LIGHTGRAY = '\033[37m'

a= '''
  ,---.  ,--.    ,----.    ,-----. 
 /  O  \ |  |   '  .-./   '  .-.  '                       
|  .-.  ||  |   |  | .---.|  | |  |
|  | |  ||  '--.'  '--'  |'  '-'  '
`--' `--'`-----' `------'  `-----' 
        ,--.  ,--.,------.,--.   ,------. ,------.,------. 
        |  '--'  ||  .---'|  |   |  .--. '|  .---'|  .--. ' 
        |  .--.  ||  `--, |  |   |  '--' ||  `--, |  '--'.' 
        |  |  |  ||  `---.|  '--.|  | --' |  `---.|  |\  \  
        `--'  `--'`------'`-----'`--'     `------'`--' '--'
        Version 1.0.0

-Fundamental Algorithms 
-Data Structures 
-Design Patterns
-Use Cases & Concepts
-Examples
- & more in Python.

Reference tool right in your terminal!


'''

b='''

         _.-"""-._
    _.-""         ""-._
  :"-.α  algohelper  Ω.-":
  '"-_"-._v.1.0.0_.-".-"'
    ||T+._"-._.-"_.-"|
    ||:   "-.|.-" : ||
    || .   ' :|  .  ||
    ||  .   '|| .   ||
    ||   ';.:||'    ||
    ||    '::||     ||
    ||      )||     ||
    ||     ':||     ||
    ||   .' :||.    ||
    ||  ' . :||.'   ||
    ||.'-  .:|| -'._||
  .-'": .::::||:. : "'-.
  :"-.'::::::||::'  .-":
   "-."-._"--:"  .-".-"
      "-._"-._.-".-"         
          "-.|.-"

'''

art = (a,b)



def display_main_menu():
  # Split both ASCII arts into lines
    a_lines = a.split('\n')
    b_lines = b.split('\n')

    # Determine the maximum number of lines
    max_lines = max(len(a_lines), len(b_lines))

    # Pad the shorter ASCII art with empty lines
    a_lines += [''] * (max_lines - len(a_lines))
    b_lines += [''] * (max_lines - len(b_lines))

    # Join the lines side by side
    combined_art = '\n'.join(f"{a_line:<60}{b_line}" for a_line, b_line in zip(a_lines, b_lines))

    print(bcolors.OKYELLOW + combined_art)
    print(f"{bcolors.UNDERLINE}Algohelper - Basic Algorithms and Data Structures in Python{bcolors.ENDC}")
    print(bcolors.HEADER + "\nCategories:")
    print(bcolors.OKYELLOW +"  1. Sorting algorithms")
    print(bcolors.OKYELLOW +"  2. Search algorithms")
    print(bcolors.OKYELLOW +"  3. Data structures")
    print(bcolors.OKYELLOW +"  4. String algorithms")
    print(bcolors.OKYELLOW +"  5. Graph algorithms")
    print(bcolors.OKYELLOW +"  6. Dynamic Programming")
    print(bcolors.OKYELLOW +"  0. Exit")
    return input(bcolors.LIGHTGRAY +"\nEnter your choice (0-6): ")

def display_submenu(category):
    print(f"\n{bcolors.HEADER}{category.capitalize()} Algorithms:{bcolors.ENDC}")
    items = get_items(category)
    for i, item in enumerate(items, 1):
        print(f"  {i}. {item}")
    print("  0. Back to main menu")
    return input("\nEnter your choice (0-{}): ".format(len(items)))

def get_items(category):
    return {
        "sorting": ["bubble_sort", "quicksort", "mergesort"],
        "search": ["binary_search", "linear_search"],
        "ds": ["stack", "queue", "linked_list"],
        "string": ["kmp"],
        "graph": ["dfs", "bfs"],
        "dp": ["fibonacci", "longest_common_subsequence"]
    }.get(category, [])

def sorting_algorithms(algo):
    algorithms = {
        "bubble_sort": """
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
    return arr

    Bubble sort is simple to implement and understand, making it useful for educational purposes. 
    It's best for small datasets or nearly sorted arrays, but inefficient for large, unsorted lists.
""",
        "quicksort": """
def quicksort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quicksort(left) + middle + quicksort(right)

    Quicksort is efficient for large datasets and is widely used as a general-purpose sorting algorithm. 
    It performs well on average but can have poor performance in worst-case scenarios 
    with already sorted or reverse sorted arrays.
""",
        "mergesort": """
def mergesort(arr):
    if len(arr) <= 1:
        return arr
    
    mid = len(arr) // 2
    left = mergesort(arr[:mid])
    right = mergesort(arr[mid:])
    
    return merge(left, right)

def merge(left, right):
    result = []
    i, j = 0, 0
    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1
    result.extend(left[i:])
    result.extend(right[j:])
    return result

    Mergesort is stable and guarantees O(n log n) time complexity, 
    making it suitable for sorting linked lists or when consistent performance is required. 
    It's also useful in external sorting where data doesn't fit in memory.
"""
    }
    return bcolors.OKYELLOW + algorithms.get(algo, "Sorting algorithm not found.")

def search_algorithms(algo):
    algorithms = {
        "binary_search": """
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1

    Binary search is highly efficient for searching in sorted arrays, with O(log n) time complexity. 
    It's commonly used in databases, finding entries in phone books, or any scenario 
    where quick lookups in ordered data are needed
""",
        "linear_search": """
def linear_search(arr, target):
    for i, value in enumerate(arr):
        if value == target:
            return i
    return -1

    Linear search is simple and works on unsorted lists, making it useful when the dataset is small or 
    when the list is unlikely to be searched often. 
    It's also used when searching for elements with specific properties 
    that can't be leveraged by more efficient algorithms.
"""
    }
    return bcolors.OKYELLOW + algorithms.get(algo, "Search algorithm not found.")

def ds_algorithms(ds):
    structures = {
        "stack": """
class Stack:
    def __init__(self):
        self.items = []

    def push(self, item):
        self.items.append(item)

    def pop(self):
        if not self.is_empty():
            return self.items.pop()

    def is_empty(self):
        return len(self.items) == 0

    def peek(self):
        if not self.is_empty():
            return self.items[-1]

    def size(self):
        return len(self.items)

    Stacks are used for managing function calls in programming languages, 
    implementing undo mechanisms, and parsing expressions. 
    They're also useful in depth-first search algorithms 
    and for solving problems like balancing parentheses
""",
        "queue": """
from collections import deque

class Queue:
    def __init__(self):
        self.items = deque()

    def enqueue(self, item):
        self.items.append(item)

    def dequeue(self):
        if not self.is_empty():
            return self.items.popleft()

    def is_empty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)

    Queues are used in breadth-first search algorithms, managing tasks in operating systems, 
    and handling asynchronous data transfer. 
    They're also useful in scenarios like print job scheduling or 
    any first-in-first-out (FIFO) requirement.
""",
        "linked_list": """
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, val):
        if not self.head:
            self.head = ListNode(val)
            return
        curr = self.head
        while curr.next:
            curr = curr.next
        curr.next = ListNode(val)

    def print_list(self):
        curr = self.head
        while curr:
            print(curr.val, end=" -> ")
            curr = curr.next
        print("None")

    Linked lists are useful for implementing dynamic data structures where frequent insertions 
    and deletions are required. 
    They're used in implementing other data structures like stacks, queues, and hash tables, a
    nd are beneficial when memory allocation needs to be dynamic.

"""
    }
    return bcolors.OKYELLOW + structures.get(ds, "Data structure not found.")

def string_algorithms(algo):
    algorithms = {
        "kmp": """
def kmp_search(text, pattern):
    def compute_lps(pattern):
        lps = [0] * len(pattern)
        length = 0
        i = 1
        while i < len(pattern):
            if pattern[i] == pattern[length]:
                length += 1
                lps[i] = length
                i += 1
            else:
                if length != 0:
                    length = lps[length - 1]
                else:
                    lps[i] = 0
                    i += 1
        return lps

    lps = compute_lps(pattern)
    i = j = 0
    while i < len(text):
        if pattern[j] == text[i]:
            i += 1
            j += 1
        if j == len(pattern):
            print(f"Pattern found at index {i - j}")
            j = lps[j - 1]
        elif i < len(text) and pattern[j] != text[i]:
            if j != 0:
                j = lps[j - 1]
            else:
                i += 1

    KMP is efficient for string matching problems, especially when the pattern occurs multiple times in the text. 
    It's used in text editors for find/replace operations, in bioinformatics for 
    DNA sequence matching, and in network security for intrusion detection systems.
"""
    }
    return bcolors.OKYELLOW + algorithms.get(algo, "String algorithm not found.")

def graph_algorithms(algo):
    algorithms = {
        "dfs": """
def dfs(graph, start, visited=None):
    if visited is None:
        visited = set()
    visited.add(start)
    print(start, end=' ')
    for neighbor in graph[start]:
        if neighbor not in visited:
            dfs(graph, neighbor, visited)

    DFS is used for traversing or searching tree or graph data structures. 
    It's applied in solving maze problems, detecting cycles in graphs, topological sorting, 
    and finding connected components in a graph.
""",
        "bfs": """
from collections import deque

def bfs(graph, start):
    visited = set()
    queue = deque([start])
    visited.add(start)

    while queue:
        vertex = queue.popleft()
        print(vertex, end=' ')
        for neighbor in graph[vertex]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)

    BFS is used for finding the shortest path in unweighted graphs. 
    It's applied in social networking applications to find degrees of separation, in GPS systems for 
    finding nearby locations, and in puzzle-solving algorithms like Rubik's cube solvers
"""
    }
    return bcolors.OKYELLOW + algorithms.get(algo, "Graph algorithm not found.")

def dp_algorithms(algo):
    algorithms = {
        "fibonacci": """
def fibonacci(n):
    if n <= 1:
        return n
    dp = [0] * (n + 1)
    dp[1] = 1
    for i in range(2, n + 1):
        dp[i] = dp[i - 1] + dp[i - 2]
    return dp[n]

    The dynamic programming approach to Fibonacci is used to efficiently calculate Fibonacci numbers, 
    avoiding the exponential time complexity of naive recursive solutions. 
    This technique is also applied in solving optimization problems and in financial modeling.
""",
        "longest_common_subsequence": """
def lcs(X, Y):
    m, n = len(X), len(Y)
    L = [[0] * (n + 1) for _ in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i-1] == Y[j-1]:
                L[i][j] = L[i-1][j-1] + 1
            else:
                L[i][j] = max(L[i-1][j], L[i][j-1])
    return L[m][n]

    LCS is used in diff utilities for file comparison, in bioinformatics for comparing genetic sequences, 
    and in natural language processing for detecting plagiarism. 
    It's also applied in version control systems to reconcile changes in documents.
"""
    }
    return bcolors.OKYELLOW + algorithms.get(algo, "Dynamic programming algorithm not found.")

def main():
    while True:
        choice = display_main_menu()
        if choice == '0':
            print(f"{bcolors.OKYELLOW}Thank you for using Algohelper. Goodbye!{bcolors.ENDC}")
            break
        elif choice in ['1', '2', '3', '4', '5', '6']:
            category = ['sorting', 'search', 'ds', 'string', 'graph', 'dp'][int(choice) - 1]
            while True:
                subchoice = display_submenu(category)
                if subchoice == '0':
                    break
                items = get_items(category)
                if 1 <= int(subchoice) <= len(items):
                    item = items[int(subchoice) - 1]
                    print(f"\n{bcolors.LIGHTGRAY}Algorithm: {item}{bcolors.ENDC}")
                    print(eval(f"{category}_algorithms('{item}')"))
                    input(bcolors.LIGHTGRAY + "\nPress Enter to continue...")
                else:
                    print(f"{bcolors.FAIL}Invalid choice. Please try again.{bcolors.ENDC}")
        else:
            print(f"{bcolors.FAIL}Invalid choice. Please try again.{bcolors.ENDC}")

if __name__ == "__main__":
    main()
