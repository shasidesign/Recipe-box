 <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Recipe Box</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 20px;
            background-color: #f8f0e3;
            color: #333;
        }

        h1 {
            color: #8e44ad;
            text-align: center;
            margin-bottom: 20px;
        }

        .recipe-box {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 20px;
        }

        .recipe {
            border: none;
            padding: 20px;
            background-color: #fff;
            box-shadow: 5px 5px 12px rgba(0, 0, 0, 0.15);
            border-radius: 12px;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .recipe:hover {
            transform: translateY(-8px);
            box-shadow: 8px 8px 18px rgba(0, 0, 0, 0.2);
        }

        .recipe img {
            max-width: 100%;
            height: auto;
            margin-bottom: 15px;
            border-radius: 8px;
            box-shadow: 3px 3px 8px rgba(0, 0, 0, 0.1);
        }

        .recipe h2 {
            color: #27ae60;
            margin-bottom: 10px;
        }

        .ingredients {
            margin-bottom: 15px;
        }

        .ingredients ul {
            list-style-type: disc;
            padding-left: 20px;
            color: #555;
        }

        .instructions {
            color: #7f8c8d;
        }

        .recipe p{
            color:#7f8c8d;
        }

        #search-bar {
            padding: 10px;
            margin: 20px auto;
            display: block;
            width: 80%;
            max-width: 400px;
            border-radius: 5px;
            border: 1px solid #ccc;
            font-size: 16px;
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.6);
            z-index: 1000;
        }

        .modal-content {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            max-width: 600px;
            margin: 100px auto;
        }

        .close {
            color: #aaa;
            font-size: 28px;
            font-weight: bold;
            position: absolute;
            top: 10px;
            right: 20px;
            cursor: pointer;
        }

        .close:hover,
        .close:focus {
            color: #000;
            text-decoration: none;
            cursor: pointer;
        }

        .favorite-btn {
            color: #e74c3c;
            cursor: pointer;
            font-size: 18px;
        }

        .favorite-btn.active {
            color: #f39c12;
        }

        #random-recipe-btn {
            display: block;
            margin: 20px auto;
            padding: 10px 20px;
            background-color: #8e44ad;
            color: #fff;
            border: none;
            border-radius: 8px;
            cursor: pointer;
        }

        #random-recipe-btn:hover {
            background-color: #9b59b6;
        }
    </style>
</head>
<body>

    <h1>Global Cafe</h1>

    <input type="text" id="search-bar" placeholder="Search recipes..." />

    <button id="random-recipe-btn">Show Random Recipe</button>

    <div class="recipe-box">
        <div class="recipe" id="recipe1">
            <h2>Chocolate Chip Cookies</h2>
            <img src="https://cafeniloufer.com/cdn/shop/products/ChocoChip_1024x1024.jpg?v=1647518005" width="100" height="100">
            <div class="ingredients">
                <ul>
                    <li>1 cup (2 sticks) unsalted butter, softened</li>
                    <li>¾ cup granulated sugar</li>
                    <li>¾ cup packed brown sugar</li>
                    <li>1 teaspoon vanilla extract</li>
                    <li>2 large eggs</li>
                    <li>2 ¼ cups all-purpose flour</li>
                    <li>1 teaspoon baking soda</li>
                    <li>1 teaspoon salt</li>
                    <li>2 cups semi-sweet chocolate chips</li>
                </ul>
            </div>
            <p class="instructions">Preheat oven to 375 degrees F (190 degrees C). Cream together the butter, granulated sugar, and brown sugar until smooth...</p>
            <span class="favorite-btn">&#9733;</span>
        </div>

        <div class="recipe" id="recipe2">
            <h2>Spaghetti with Marinara Sauce</h2>
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ5bnXQgExVSFPay6pZzlGrzQAesM5h749XFQ&s" width="100" height="100">
            <div class="ingredients">
                <ul>
                    <li>1 pound spaghetti</li>
                    <li>1 tablespoon olive oil</li>
                    <li>1 onion, chopped</li>
                    <li>2 cloves garlic, minced</li>
                    <li>28 ounces crushed tomatoes</li>
                    <li>1 teaspoon dried oregano</li>
                    <li>½ teaspoon dried basil</li>
                    <li>Salt and pepper to taste</li>
                </ul>
            </div>
            <p class="instructions">Cook spaghetti according to package directions. Meanwhile, heat olive oil in a large saucepan over medium heat. Add onion and cook...</p>
            <span class="favorite-btn">&#9733;</span>
        </div>

        <div class="recipe" id="recipe3">
            <h2>Chicken Stir-Fry</h2>
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT1qvw12bzQ1XelX_NuvI0at2UYyPvxTu8Cdw&s" width="100" height="100">
            <div class="ingredients">
                <ul>
                    <li>1 pound boneless, skinless chicken breasts, cut into bite-sized pieces</li>
                    <li>1 tablespoon soy sauce</li>
                    <li>1 tablespoon cornstarch</li>
                    <li>2 tablespoons vegetable oil</li>
                    <li>1 onion, sliced</li>
                    <li>2 cloves garlic, minced</li>
                    <li>1 red bell pepper, sliced</li>
                    <li>1 green bell pepper, sliced</li>
                    <li>1 cup broccoli florets</li>
                </ul>
            </div>
            <p class="instructions">In a small bowl, combine chicken, soy sauce, and cornstarch. Heat vegetable oil in a large skillet over medium-high heat...</p>
            <span class="favorite-btn">&#9733;</span>
        </div>

        <div class="recipe" id="recipe4">
            <h2>Pancakes</h2>
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT2DT1D7fmBvlcxoe2rv6mjGd1yXj8WUS4YgQ&s" width="100" height="100">
            <div class="ingredients">
                <ul>
                    <li>1 ½ cups all-purpose flour</li>
                    <li>3 ½ teaspoons baking powder</li>
                    <li>1 teaspoon salt</li>
                    <li>1 tablespoon white sugar</li>
                    <li>1 ¼ cups milk</li>
                    <li>1 egg</li>
                    <li>3 tablespoons melted butter</li>
                </ul>
            </div>
            <p class="instructions">In a large bowl, whisk together flour, baking powder, salt, and sugar. In a separate bowl, whisk together milk, egg, and melted butter...</p>
            <span class="favorite-btn">&#9733;</span>
        </div>

    </div>

    <!-- Modal -->
    <div id="recipe-modal" class="modal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <h2 id="modal-title"></h2>
            <div id="modal-ingredients"></div>
            <p id="modal-instructions"></p>
        </div>
    </div>

    <script>
        // Toggle instructions visibility
        const recipes = document.querySelectorAll('.recipe');
        recipes.forEach(recipe => {
            recipe.addEventListener('click', () => {
                const instructions = recipe.querySelector('.instructions');
                instructions.style.display = (instructions.style.display === 'none' || instructions.style.display === '') ? 'block' : 'none';
            });
        });

        // Search functionality
        const searchInput = document.getElementById('search-bar');
        searchInput.addEventListener('input', function() {
            const searchQuery = searchInput.value.toLowerCase();
            recipes.forEach(recipe => {
                const title = recipe.querySelector('h2').textContent.toLowerCase();
                recipe.style.display = title.includes(searchQuery) ? 'block' : 'none';
            });
        });

        // Modal Functionality
        const modal = document.getElementById("recipe-modal");
        const closeModal = document.querySelector(".close");

        recipes.forEach(recipe => {
            recipe.addEventListener("click", () => {
                const title = recipe.querySelector("h2").textContent;
                const ingredients = recipe.querySelector(".ingredients").innerHTML;
                const instructions = recipe.querySelector(".instructions").textContent;

                document.getElementById("modal-title").textContent = title;
                document.getElementById("modal-ingredients").innerHTML = ingredients;
                document.getElementById("modal-instructions").textContent = instructions;

                modal.style.display = "block";
            });
        });

        closeModal.addEventListener("click", () => {
            modal.style.display = "none";
        });

        window.addEventListener("click", event => {
            if (event.target === modal) {
                modal.style.display = "none";
            }
        });

        // Random Recipe Button
        const randomRecipeButton = document.getElementById('random-recipe-btn');
        randomRecipeButton.addEventListener('click', () => {
            const randomRecipe = recipes[Math.floor(Math.random() * recipes.length)];
            randomRecipe.scrollIntoView({ behavior: 'smooth' });
        });

        // Favorite Button Toggle
        const favoriteButtons = document.querySelectorAll('.favorite-btn');
        favoriteButtons.forEach(button => {
            button.addEventListener('click', () => {
                button.classList.toggle('active');
            });
        });
    </script>

</body>
</html>

