import React, { useState } from "react";
import axios from "axios";

function SearchBar() {
  const [searchTerm, setSearchTerm] = useState("");
  const [searchResults, setSearchResults] = useState([]);

  const handleInputChange = (event) => {
    setSearchTerm(event.target.value);
  };

  const handleSearch = () => {
    axios
      .get(`https://api.spoonacular.com/recipes/findByIngredients?ingredients=${searchTerm}&apiKey=YOUR_API_KEY`)
      .then((response) => {
        setSearchResults(response.data);
      })
      .catch((error) => {
        console.error(error);
      });
  };

  return (
    <div>
      <input type="text" value={searchTerm} onChange={handleInputChange} />
      <button onClick={handleSearch}>Search</button>
      {searchResults.map((recipe) => (
        <div key={recipe.id}>
          <h3>{recipe.title}</h3>
          <img src={`https://spoonacular.com/recipeImages/${recipe.id}-90x90.jpg`} alt={recipe.title} />
        </div>
      ))}
    </div>
  );
}

export default SearchBar;
