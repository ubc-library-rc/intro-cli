---
 layout: default
 title: Automating with loops
 parent: Outline
 nav_order: 3
---

Sometimes you want to do a lot quickly. Loops are a way to automate a series of commands so that you batch together.

The structure of a loop is:

~~~
for thing in list_of_things
do
  operation_using $thing #Indentation is not required but helps legibility.
done
~~~

Applied in an example, this looks like:

~~~
for filename in *.doc
do
  echo "$filename"
  cp "$filename" backup_"$filename"
done
~~~

Notice that as you write a loop in the shell the indicator changes from $ to > which basically means "waiting for the command to finish".

In this example we are saying that every time a filename has the ".doc" extension, we want to take the name of the file, and then make a copy of it while prefixing the file with "backup_". The result is a backup of every file with a .doc extension in our directory.

Let's say we make four files called

Input
{: .label .label-green}
~~~
touch one.doc two.doc three.doc four.doc
~~~

Run our loop and see what happens.

Input
{: .label .label-green}
~~~
backup_one.doc
backup_two.doc
backup_three.doc
backup_four.doc
~~~
