
- week1
    - tuesday
	- hella stories of how language matters
	      - prolog, elixr rlang, actors
	      - the acm com paper
	      - the pige story
	      - make (dependencies)
	      - cognitive theory and languages
    - thursday, set up day. eveyone try to bring a laptop
         - one repo per group
	 - one repo per student
	 - tim andgetting a python/github environment going

week2 
    - tueday : in house test
    - thursday: pthon tutorial starts. example. ey wrk on cntxt. chapter5 of lopes
- intro to Python
- the classics
     - LISP
     - Prolog
     - Smalltalk

week N
- DSLS
   markdown
homework

- Intro python
- shunting yard
- State machine
- Compartmental models
- production rules

# Ideas

## projects

markdown
mustache
minikaren
lisp

## package management for ok


## Systems
- travis integration
- mysql integration
- find standard libraries. implement them
   - mustache
   - markdown
   - xml library
   - json library
   - stats
   - collections
   - the jamie 17
       https://github.com/jamiejennings/rosie-pattern-language/blob/tranche-2/src/core/list.lua
       Tests/examples are in:
       https://github.com/jamiejennings/rosie-pattern-language/blob/tranche-2/src/list-test.lua
- modes for vim, emacs, and what ever else is in the
  language dejour
        - time to struggle with viml, elisp, etc
	- what should a mode do?
        - long string highlighting
	- markdown highting within a string
	- lints. what lints?
	- reformat (to arnold's standards)
- Jypter   notepbppks

Port little languages

- miniKaren
- Norvig's lisp

closures (is that even possible?)

Add an OO layer

polymorphism
- static: if the LAST thing in "." chain is a ( then
  at load time, do the lookup  (assumes that all files
  have "safe" BEGIN statements and that methods defined
  before used; e.g. superclassed before sub-classes
  )
- dynamic: ?
- add "function Num.fred" notation

anyway to garbage collect instance memory ?
- if not, what is the cost? (dude, we are not writing operating
  systems here). ? a linit for local vars that are objects?

not multiple inheritance

```
BEGIN { 
  OK.instances.id=0
}
function isa(class1,class2) {
  OK.instances.exists[class1]
  OK.instances.exists[class2]
  OK.instances.parent[class2] = class1
}
function new(i,class,   id,tmp) {
  if (class=='') class='lobby'
  ++OK.instances.exists[class]
  id = class ++OK.instances.exists[class]
  OK.instances.isa[id] = class
  return id
}
function call(i,what,a,b,c,d,e,f,g,h,i,j,k,l,m) {
  class = OK.instances.isa[i] 
  return call1(OK.instances.is[i],what,
                 a,b,c,d,e,f,g,h,i,j,k,l,m)
}
function call1(class,x,what,a,b,c,d,e,f,g,h,i,j,k,l,m) {
  if (class=="") NOclass()
  if (what in OK.instances[class].does)
     return funcall(OK.instances[x].does,x,
                    a,b,c,d,e,f,g,h,i,j,k,l,m)
  else if (class in OK.instances.parent) {
     return call1(OK.instances.parent[class],
                  x,what,
                  a,b,c,d,e,f,g,h,i,j,k,l,m)
  else NOmethodfound()
}
function funcall(f,a,b,c,d,e,f,g,h,i,j,k,l,m) {
  if (a=='') return @f()
  if (b=='') return @f(a)
  if (c=='') return @f(a,b)
  if (d=='') return @f(a,b,c)
  if (e=='') return @f(a,b,c,d)
  if (f=='') return @f(a,b,c,d,e)
  if (g=='') return @f(a,b,c,d,e,f)
  if (h=='') return @f(a,b,c,d,e,f,g)
  if (i=='') return @f(a,b,c,d,e,f,g,h)
  if (j=='') return @f(a,b,c,e,e,f,g,h,i)
  if (k=='') return @f(a,b,c,e,e,f,g,h,i,j)
  if (l=='') return @f(a,b,c,d,e,f,g,h,i,j,k)
  if (m=='') return @f(a,b,c,d,e,f,g,h,i,j,k,l)
  return            @f(a,b,c,d,e,f,g,h,i,j,k,l,m)

}
```


