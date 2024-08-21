# Like python but with types and better event handling and also compiled

Example code:

```Redlang

int x = 5  # Dynamically sized int
uint64 y = 4  # Specified int type

mut List[int] test = [1, 2, 3, 4]
mut List test = [5, 6, 'hello', 3.0]
mut List[int][4] test = [1, 2, 3, 4]  # Fixed length

type listType = type([1, 2, 3, 4])
listType.length == 4  # True
listType.subtype == int  # True


test[3] = 5  # OK
test += 6 # Not ok

(x, y, z) -> x + y + z  # lambda function

List[_T]

add(x, y, z) -> x + y + z  # inline function

# add is of the type Func[Tuple[3] -> Tuple[3]]
int add(int x, int y, int z) -> x + y + z
# add is now of the type Func[Tuple[3] -> Int]

for i in 1:3 {
	stuff happens
	more stuff happens
}
# iterator is deleted outside of the for loop.

```



# New thoughts

Functions should be more mathematical, and be described in terms of mathematical function type notation

```Redlang

int add(int a, int b, int c = 4) = a + b + c

type(add)  # Function((int, int, opt(int)) -> int]

```


Tuple is a type with fixed length and a fixed type for each entry

Args is a subtype of tuple which doesn't show with parens around them



