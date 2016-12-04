Instruction to run :-
                    --> A web browser is required.
                    --> Just open index.html in web browser, nothing special has to be done.

Optimizations made by me in "index.html"
                    --> style.css is minified and then placed directly into style tag inside head tag.
                    --> print.css is only used when the page has to be printed. Therefore media attribute is added inside link tag linking print.css
                    --> analytics.js and perfmatters.js , both javascripts has been assigned to "async" so that it runs at last.
                    --> pizzeria image is changed to pizzeria-small in img tag, as the image displayed in page is small therfore there is no need to load the larger version.

Optimizations made by me in "views/js/main.js"
		    --> FOR OPTIMIZING SLIDER MOVEMENT
                    --> document.querySelectorAll(".randomPizzaContainer") is assigned to a new variable(pizzaSelectionAtOnce) outside loop beacause of its multiple occurances inside the loop.
                    --> function determineDx is completely removed beacuse its complex and unnecessary functionality.
		    --> a new switch is used inside changePizzaSizes function to select the desired size of pizza.
		    --> the new assigned value to a new variable(newWidth) inside switch is then used inside loop to change the size of all the pizzas.

                    --> FOR OPTIMIZING FRAME RATE 
                    --> var items = document.querySelectorAll('.mover') is moved outside the function as there is no need to calculate it every time the function updatePositions is called.
		    --> var items = document.querySelectorAll('.mover') is declared after the pizzas has been created, therefore it is after the function creating all pizzas as the last line of script.
		    --> var long = items.length, a new variable is created outside the for loop in updatePositions() to store the length of the array of items returned by var items( = document.querySelectorAll('.mover')).
		    --> var phaseOut = document.body.scrollTop / 1250, new variable phaseOut is created to store the value of (document.body.scrollTop / 1250) and get it done outside of the loop.
		    --> the image of background pizzas is being replaced by a compressed image, manely pizza-mini.
		    --> Number of pizzas is reduced to 30 from 200.

Optimizations made by me in "views/pizza.html"
		    --> the size of pizzeria image is heavily reduced and then compressed to get the optimum performance. 