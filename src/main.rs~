// See example in Module std::boxed

// Recursive structures must be boxed.
// Unfortunately, the following doesn't work.
//     Cons(T, List<T>)
// The size of a list depends on its length, so we don't
// know how much memory to allocate for Cons.
// By introducing a Box, which has a defined size,
// we know how big Cons needs to be.

// The compiler is capable of providing basic implementations for some traits
// via the #[deriv] attribute.
// The Debug trait allows List to be formatted using {:?}
#[derive(Debug)]
enum List<T> {
    Cons(T, Box<List<T>>),
    Nil,
}
pub enum FoundError {
       NotFoundError, 
    }
// If add() is not used, this attribute suppresses the compiler warning message
#[allow(dead_code)]
impl<'a, T> List<T> {
//    fn iter(&'a self) -> ListIterator<'a, T> {
//        ListIterator{cur: self}
//    }
    fn add(self, elem: T) -> List<T> {
        List::Cons(elem, Box::new(self))
    }
    fn car(self) -> Option<T> {  // in progress
        match self {
            List::Cons(u,_v) => Some(u),
            List::Nil        => None,
        }
    }
fn cdr(self) -> Option<List<T>> {
        match self {
            List::Cons(_u,v) => Some(*v),
            List::Nil         => None,
        }
    }
fn len(&self) ->i32
{
match *self{
List::Cons(_,ref v)=>1+v.len(),
List::Nil=>0,
}
}

fn element(self,n:i32)->Option<T>
{
//println!("{:?}", self.car().unwrap());
match self
{
List::Nil=>None,
List::Cons(u,v) =>match n
{
0 => Some(u),
_=>Some(*v).unwrap().element(n-1),
},
}
}

fn removeFirst(self,s:T)->Option<List<T>>
{
match self
{
List::Nil=>None,
List::Cons(u,v) => match u
{
s=>Some(*v),
_=>Some(List::Cons(u,v.removeFirst(s)))

},
}
}
}
// Is there a way to define List.new() ?

fn main() {
    let list: List<i32> = List::Cons(1, Box::new(List::Cons(2, Box::new(List::Nil))));
    println!("{:?}", list);
 println!("{:?}", list.cdr().unwrap());
    let l = List::Nil.add(1).add(2).add(3).add(5);
    println!("{:?}", l);
 println!("{:?}", l.len());
let ele=List::Nil.add(10).add(20).add(30).add(40);
println!("{:?}", ele);
 println!("{:?}", ele.element(1));
println!("{:?}",ele.removeFirst(20));
 //println!("{:?}", l.cdr().unwrap());
    println!("{:?}", l.car().unwrap());


}
