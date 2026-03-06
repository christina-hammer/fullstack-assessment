 Stackline Full Stack Assessment - Kit Hammer

---Bug Fixes---

Bug Location: Product list page - category filter dropdowns
Bug Description: When filtering products by category, the 'Subcategories' drop down shows the top-level list of categories
Fix: 
Reasoning for fix:

Bug Location: Product list page - category filter dropdowns
Bug Description: When a category filter is selected and then the 'Clear Filters' button is clicked, the previously selected category is still shown as selected on the 'Categories' drop down. The category filter does not remain applied to the search results, but the category name is displayed instead of being cleared.
Fix: 
Reasoning for fix:

Bug Location: Product list page
Bug Description: Search results only show first 20 products with no way to scroll or page through the rest of the results. 
Fix: 
Reasoning for fix:

Bug Location: Product list page
Bug Description: Number of search results shown is a reflection of the number of results being displayed on the page instead of the total number of results
Fix: 
Reasoning for fix:


**Bug Location: Product list page - search bar
Bug Description: When attempting to enter search query, a run time error sometimes occurs. Need more info to determine exact repro. Appears related to img src.
Fix: 
Reasoning for fix:

Bug Location: Product list page - search result tiles
Bug Description: The 'View Details' button on each tile is located directly below the product description and tags instead of being anchored to the bottom of the tile. 
This causes the 'View Details' button for each tile to be misaligned vertically which looks bad
Fix: 
Reasoning for fix:

**Bug Location: Throughout application
Bug Description: Check contrast ratio between grey text and white background. Might break accessibility guidelines.
Fix: 
Reasoning for fix:

Bug Location: 
Bug Description: 
Fix: 
Reasoning for fix:


---Improvements/Enhancements---

Location of change: Product list page - search bar
Description of change: Adding debounce to search so API isn't called instantly for every character typed
Reason for change:
Implementation notes:

Location of change: Product detail page
Description of change: Display price of product
Reason for change:
Implementation notes:

Location of change: Product list page
Description of change: Display price of products
Reason for change:
Implementation notes:

Location of change: Product list page
Description of change: Add price-based filtering
Reason for change:
Implementation notes:
