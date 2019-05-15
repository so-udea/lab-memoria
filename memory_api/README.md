# Memory API # 
In this homework, you will gain some familiarity with memory allocation. First, you’ll write some buggy programs (fun!). Then, you’ll use some tools to help you find the bugs you inserted. Then, you will realize how awesome these tools are and use them in the future, thus making yourself more happy and productive. The tools are the debugger (e.g., gdb), and a memory-bug detector called valgrind [SN05].

## Questions ##
1. First, write a simple program called null.c that creates a pointer to an integer, sets it to NULL, and then tries to dereference it. Compile this into an executable called null. What happens when you run this program?

Escriba un programa simple llamado ```null.c``` que cree un puntero a un entero, llevelo a null y entonces intente desreferenciarlo. Compile este programa llamado ```null```. ¿Que pasa cuando usted ejecuta este programa?

2. Next, compile this program with symbol information included (with the -g flag). Doing so let’s put more information into the executable, enabling the debugger to access more useful information about variable names and the like. Run the program under the debugger by typing gdb null and then, once gdb is running, typing run. What does gdb show you?

Compile el programa del ejercicio anterior usando información de simbolos (con la flag -g). Al hacer esto se esta poniendo mas informacion en el ejecutable para permitir al debugger acceder a informacion util sobre los nombres de las variables y cosas similares. Ejecute el programa bajo el debugger digitando en consola (para el caso) ```gdb null``` y entonces una vez el ```gdb``` este corriendo ejecute ```run```. ¿Que muestra gdb?

3. Finally, use the valgrind tool on this program. We’ll use the memcheck tool that is a part of valgrind to analyze what happens. Run this by typing in the following: valgrind --leak-check=yes null. What happens when you run this? Can you interpret the output from the tool?

Haga uso de la herramienta ```valgrind``` en el programa empleado en los puntos anteriores. Se usará la herramienta ```memcheck``` que es parte de ```valgrind``` para analizar lo que pasa: ``` valgrind --leak-check=yes null```. ¿Que pasa cuando corre esto?, ¿Puede usted interpretar la salida de la herramienta anterior?

4. Write a simple program that allocates memory using malloc() but forgets to free it before exiting. What happens when this program runs? Can you use gdb to find any problems with it? How about valgrind (again with the --leak-check=yes flag)?

Escriba un programa sencillo que asigne memoria usando ```malloc()``` pero olvide liberarla antes de que el programa termina. ¿Que pasa cuando este programa se ejecuta?, ¿Puede usted usar gdb para encontrar problemas como este?, ¿Que dice acerca de Valgrind (de nuevo use este con la bandera ```--leak check=yes```)?

5. Write a program that creates an array of integers called data of size 100 using malloc; then, set data[100] to zero. What happens when you run this program? What happens when you run this program using valgrind? Is the program correct?

Escriba un programa que cree un array de enteros llamado data de un tamaño de 100 usando ```malloc```; entonces, lleve el ```data[100]``` a ```0```. ¿Que pasa cuando este programa se ejecuta?, ¿Que pasa cuando se corre el programa usando ```valgrind```?, ¿El programa es correcto?

6. Create a program that allocates an array of integers (as above), frees them, and then tries to print the value of one of the elements of the array. Does the program run? What happens when you use ```valgrind``` on it?

Codifique un programa que asigne un array de enteros (como arriba), luego lo libere, y entonces intente imprimir el valor de un elemento del array. ¿El programa corre?, ¿Que pasa cuando hace uso de ```valgrind```?

7. Now pass a funny value to free (e.g., a pointer in the middle of the array you allocated above). What happens? Do you need tools to find this type of problem?


Ahora pase un **funny value** para liberar (e.g. un puntero en la mitad del array que usted ha asignado) ¿Que pasa?, ¿Usted necesita herramientas para encontrar este tipo de problemas?

8. Try out some of the other interfaces to memory allocation. For example, create a simple vector-like data structure and related routines that use realloc() to manage the vector. Use an array to store the vectors elements; when a user adds an entry to the vector, use realloc() to allocate more space for it. How well does such a vector perform? How does it compare to a linked list? Use valgrind to help you find bugs.

Intente usar alguna de las otras interfaces para asignacion de memoria. Por ejemplo, cree una estructura de datos simple similar a un vector y que use rutinas que usen realloc para manejar el vector. Use un array para almacenar los elementos del vector; cuando un usuario agregue una entrada al vector, use realloc para asignar un espacio mas a este. ¿Que tan bien funciona el vector asi?, ¿Como se compara con una lista enlazada?, utilice ```valgrind``` para ayudarse en la busqueda de errores.

9.  Spend more time and read about using gdb and valgrind. Knowing your tools is critical; spend the time and learn how to become an expert debugger in the UNIX and C environment.

Gaste mas tiempo y lea sobre el uso de gdb y valgrind. Conocer estas herramientas es critico; gaste el tiempo y aprenda como volverse un experto debugger en UNIX y C enviroment.


<!---
## Enlaces ##
* http://www.st.ewi.tudelft.nl/koen/ti2725-c/valgrind.pdf
* http://web.mit.edu/amcp/drg/valgrind-howto.pdf
* https://www.eneagrid.enea.it/Tutorials/Valgrind/Valgrind-HOWTO.pdf
* https://users.dcc.uchile.cl/~skreft/material/cc31a/valgrind.pdf
* http://www.liv.ic.unicamp.br/~rteixeira/ensino/valgrind.pdf
* https://aleksander.es/data/valgrind-memcheck.pdf
* http://www.phys.uconn.edu/~rozman/Courses/P2200_14F/downloads/valgrind-quick-start.pdf
* http://cs.ecs.baylor.edu/~donahoo/tools/valgrind/
* https://computing.llnl.gov/tutorials/2010.07.29.workshop/Gunter.Valgrind.pdf
* https://wr.informatik.uni-hamburg.de/_media/teaching/sommersemester_2014/cgk-14-menck-memory-leaks-presentation.pdf
* https://people.cs.clemson.edu/~levinej/courses/S15/1020/handouts/lec20/Valgrind.pdf
* ftp://ftp.sara.nl/pub/outgoing/tam2012/03_-_Tutorial_Valgrind.pdf
* http://people.ds.cam.ac.uk/pmb39/Valgrind.pdf
* http://www.valgrind.org/docs/manual/QuickStart.html
* ftp://ftp.cis.upenn.edu/pub/rtg/entcs-89-2/89.2.005.pdf
* http://toodle.cs.huji.ac.il/cs14/file.php/67316/TAs/valgrind_tut.pdf
* https://access.redhat.com/documentation/es-es/red_hat_enterprise_linux/6/html/performance_tuning_guide/s-memory-valgrind
* http://lsi.vc.ehu.eus/pablogn/docencia/manuales/Valgrind/Valgrind.pdf
* https://www.bsc.es/support/PATC-MareNostrum4/2019/PATC-Debugging-HandsOn.pdf
* http://toolsworkshop.hlrs.de/2007/TALKS/OpenMPI-Memchecker-2007.07.09.pdf
* https://support.crosscontrol.com/sites/default/files/kb/profiling_application_code_with_valgrind_for_linux.pdf
* http://vlm1.uta.edu/~alex/courses/2320/resources/Valgrind_instructions.pdf
-->