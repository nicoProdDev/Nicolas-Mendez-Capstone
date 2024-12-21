# Project Title

## MoodBites: Recipes to Match Your Mood

#### Overview

MoodBites is a unique recipe finder that suggests dishes based on the user’s current mood. Whether you’re feeling adventurous, nostalgic, or need some comfort food, the app matches your emotional state with the perfect recipe.

### Problem

People’s moods often influence what they want to eat, but finding the right dish to match how you feel can be challenging. This app simplifies the process, providing personalized and uplifting meal suggestions tailored to emotional states.

### User Profile
	•	Primary Users:
	•	Individuals who want meal suggestions that align with how they feel at the moment.
	•	Food enthusiasts who enjoy exploring recipes tied to emotions.
	•	Special Considerations:
	•	The app must provide intuitive options for selecting or describing moods (e.g., happy, tired, stressed).
	•	Recipe suggestions should include a mix of quick snacks, comfort food, and creative dishes, depending on the mood.

### Features
	1.	Mood Selection:
        Users can choose their mood from a list (e.g., happy, adventurous, relaxed) or describe it in a few words.

	2.	Recipe Suggestions:
        The app recommends recipes tailored to the selected mood, using tags like “comfort,” “fun,” “energizing,” or “soothing.”

	3.	Mood-Driven Filtering:
        Users can adjust filters like dietary preferences, preparation time, or level of complexity to refine results further.

	4.	User-Contributed Recipes:
        Community members can submit recipes and tag them with relevant moods.

	5.	Interactive Features:
        Users can upvote or comment on recipes, sharing how the dish matched their mood.

	6.	Save Favorites:
        Users can save mood-specific recipes for future inspiration.

	7.	Mood Tracker:
        A simple log to track past moods and recipes for a personalized cooking journey.

### Implementation

### Tech Stack

### Frontend:
	•	React: Regarding css we'll use sass

### Backend:
	•	Node.js with Express: To build a lightweight server for handling mood inputs, recipe suggestions, and user data.
	•	Database:
	•	MySQL

### APIs:
	•	Spoonacular API: To access a database of recipes based on tags and descriptions (as a fallback or to supplement user-contributed recipes).

### Sitemap

#### Home Page
	•	Description: A welcoming page introducing the app, explaining how to use it, and offering a search bar for mood-based recipe suggestions.
	•	Key Features:
	•	Mood selection (buttons or dropdown).
	•	Call-to-action: “Find Recipes!”

#### Mood-Based Search Page
	•	Description: A page where users input their mood or select from predefined moods. The app suggests recipes that match the selected mood.
	•	Key Features:
	•	Mood input field (text or options like happy, adventurous, stressed).
	•	Filters for dietary preferences, preparation time, etc.
	•	Display of suggested recipes as cards with titles, images, and a brief description.

#### Recipe Detail Page
	•	Description: A detailed view of a specific recipe.
	•	Key Features:
	•	Full recipe details (ingredients, steps, preparation time).
	•	Option to save the recipe to favorites.
	•	Comments section for user feedback and suggestions.

#### Contribute Recipe Page
	•	Description: A page where users can add their own recipes to the app.
	•	Key Features:
	•	Form for entering recipe title, ingredients, instructions, and mood tags.
	•	Option to upload a recipe image.

#### Favorites Page
	•	Description: A page where users can view recipes they’ve saved for future reference.
	•	Key Features:
	•	List of saved recipes with quick links to their detail pages.

#### User Profile Page
	•	Description: A page for registered users to view their account information and contributions.
	•	Key Features:
	•	Edit profile options (e.g., username, profile picture).
	•	List of recipes contributed by the user.

#### About Page
	•	Description: An informational page about the app, its purpose, and the team (or creator).
	•	Key Features:
	•	Explanation of the mood-based concept.
	•	Links to social media or contact forms.

#### Login/Sign-Up Page
	•	Description: A page for user authentication.
	•	Key Features:
	•	Options to log in or create an account using email/password or third-party providers (e.g., Google).

### Data

The app will manage several data entities, each representing a key part of the functionality. Below is a description of the data models and their relationships:

## User

Attributes:
	•	id: Unique identifier for the user.
	•	username: The user’s display name.
	•	email: User’s email for login and notifications.
	•	password: Encrypted password.
	•	profilePicture: URL of the user’s profile image (optional).
	•	favorites: List of saved recipe IDs.
	•	contributedRecipes: List of recipe IDs contributed by the user.

Relationships:
	•	One-to-Many with Recipe (a user can contribute multiple recipes).

## Recipe

Attributes:
	•	id: Unique identifier for the recipe.
	•	title: Name of the recipe.
	•	ingredients: List of required ingredients (as strings or objects).
	•	instructions: Step-by-step cooking instructions.
	•	image: URL of the recipe image.
	•	moodTags: Tags representing the mood(s) this recipe matches (e.g., happy, nostalgic).
	•	prepTime: Estimated preparation time in minutes.
	•	dietaryInfo: Tags for dietary restrictions/preferences (e.g., vegetarian, gluten-free).
	•	submittedBy: User ID of the contributor.

Relationships:
	•	Many-to-One with User (each recipe belongs to a user).
	•	Many-to-Many with Mood (a recipe can match multiple moods).

## Mood

Attributes:
	•	id: Unique identifier for the mood.
	•	name: Name of the mood (e.g., happy, stressed).
	•	description: Optional description of the mood.

Relationships:
	•	Many-to-Many with Recipe (a mood can have multiple recipes).


## Endpoints

Here’s a list of endpoints the server will implement, grouped by functionality.

User Management
	1.	Register a User
	2.	Login a User
	3.	Get User Profile
	4.	Get Recipes by Mood
	5.	Get Recipe Details
	6.	Add a New Recipe
	7.	Add Recipe to Favorites
	8.	Get User Favorites
	9.	Add Comment to Recipe

### Auth

For this project, authentication will leverage OAuth via third-party providers like Google and use Passport.js, a popular Node.js library for authentication. This approach simplifies login for users and ensures secure, scalable authentication.


### Roadmap

## Environment Setup
	•	Set up the development environment:
	•	Install Node.js, npm, and dependencies (Express, Passport.js, etc.).
	•	Create the project directory structure.
	•	Initialize a Git repository for version control.

## User Authentication (Backend)
	•	Configure Passport.js with Google OAuth.
	•	Create routes for user login/logout and authentication callback.
	•	Test authentication flow using Postman or browser.

## Basic Backend APIs
	•	Set up the /api/recipes endpoint to fetch recipes based on mood.
	•	Create a database schema for users, recipes, and moods.
	•	Seed the database with sample recipes.

## React App Setup
	•	Set up the React app using Create React App or Vite.
	•	Configure routing using React Router (e.g., Home, Recipe Details, Login pages).
	•	Create a basic layout (header, footer, and navigation).

## Authentication UI
	•	Add a “Login with Google” button on the homepage.
	•	Implement the Google OAuth flow and handle redirection to the dashboard.
	•	Store user session (using JWT or cookies).

## Mood Selection and API Integration
	•	Create a form or interactive UI to let users select their mood.
	•	Connect the mood selection to the /api/recipes endpoint and display the results.

## Recipe Details Page
	•	Fetch and display detailed information for a selected recipe.
	•	Include ingredients, instructions, and an option to favorite the recipe.

## Favorites Management
	•	Add functionality to save and display favorite recipes for authenticated users.
	•	Create an endpoint /api/users/favorites to fetch and update favorites.

## User Dashboard
	•	Design a simple dashboard to show user-specific data, like contributed recipes and favorites.

## Responsive Design
	•	Test and refine the app for mobile and desktop views.
	•	Ensure UI components adapt seamlessly to different screen sizes.

## Testing
	•	Test all endpoints using Postman to ensure API functionality.
	•	Test the frontend for any broken links or bugs.
	•	Perform user acceptance testing (UAT) to simulate real-world use.

## Deployment
	•	Deploy the backend to a cloud platform like Heroku or Render.
	•	Deploy the frontend to Netlify or Vercel.
	•	Set up environment variables (e.g., Google API keys, database URL).

## Documentation
	•	Write a README file with clear instructions on how to run the app locally.
	•	Add inline comments in the code for clarity.

## Final Review and Presentation
	•	Review the entire app for quality and completeness.
	•	Prepare a short demo to showcase key features.
