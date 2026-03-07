Stackline Full Stack Assessment - Kit Hammer

Template for documenting bug fixes

Bug Location: 
Bug Description: 
Status:
Fix: 
Reasoning for fix:
Files modified:

Template for documenting Improvements/Enhancements:

Location of change: 
Description of change: 
Status: 
Reason for change:
Implementation notes:
Files modified:


---Bug Fixes---

Bug Location: Product list page - category filter dropdowns
Bug Description: When filtering products by category, the 'Subcategories' drop down shows the top-level list of categories
Status: Fixed
Fix: Included selected category in query params for subcategories API call
Reasoning for fix: 'category' param was missing from /api/subcategories call in page.tsx. Without a category specified, API could not filter for specific subcategories
Files modified: /app/page.tsx

Bug Location: Product list page - category filter dropdowns
Bug Description: When a category filter is selected and then the 'Clear Filters' button is clicked, the previously selected category is still shown as selected on the 'Categories' drop down. The category filter does not remain applied to the search results, but the category name is displayed instead of being cleared.
Status: Fixed
Fix: Update places where selectedCategory state variable in page.tsx is being "cleared" to set value as empty string instead of undefined. Repeat changes for selectedSubCategory state variable.
Reasoning for fix: For the react-select component that is used within select.tsx, a non-selection value should not be undefined. See https://react-select.com/props#select-props
Files modified: /app/page.tsx

Bug Location: Product list page
Bug Description: Search results only show first 20 products with no way to view the rest of the results
Status: Fixed
Fix: Remove default value of 20 for limit param on 'api/products'. If no limit value specified, none will be applied
Reasoning for fix: The user should be able to see all relevant search results and not only the first 20 
Files modified: /app/page.tsx, app/api/products/route.ts

Bug Location: Product list page
Bug Description: Number of search results shown is a reflection of the number of results being displayed on the page instead of the total number of results
Status: No fix needed
Fix: -
Reasoning for fix: No fix needed because the number of results appeared to be incorrect, but was actually an accurate reflection of the number of results being returned by the products API. The issue was instead with the api call in page.tsx including a limit parameter with a default value of 20 that was removed as part of another bug fix
Files modified: -

Bug Location: Product list page
Bug Description: Runtime error caused by missing image src for one of the products
Status: Fixed
Fix: Added "images-na.ssl-images-amazon.com" hostname to next.config.ts images.remotePatterns
Reasoning for fix: This hostname is required in next.config.ts to support the image source. 
Files modified: next.config.ts

Bug Location: Throughout application styling
Bug Description: Contrast ratio between --muted color style oklch(0.5555 0 0) and white background violates WCAG 2.2 Level AAA accessibility standards for normal text
Status: Fixed
Fix: Use slightly darker shade of grey oklch(0.4459 0 0) to comply with Level AAA accessiblity standards
Reasoning for fix: Accessiblity Compliance
Files modified: app/globals.css

---Improvements/Enhancements---

Location of change: Product list page - search result product cards
Description of change: For all product cards, position 'View Details' button relative to the bottom of the card
Status: Completed
Reason for change: The 'View Details' button on each card is located directly below the product description and tags instead of being anchored to the bottom of the card. This causes the 'View Details' button for each card to be misaligned vertically which is moderately visually chaotic
Implementation notes: Added className="mt-auto" to CardFooter component of the product card 
Files modified: app/page.tsx

Location of change: Product detail page
Description of change: Display price of product
Status: Completed
Reason for change: Critical missing information for customer
Implementation notes: Added missing retailPrice property to Product interfaces and added JSX to display price value on product detail page
Files modified: app/product/page.tsx, lib/products.ts

Location of change: Product list page
Description of change: Display price of products on card
Status: Completed
Reason for change: Useful information for customer trying to search for products
Implementation notes: Added retailPrice property to Product interface on app/page.tsx. Added JSX to display price on product card
Files modified: app/page.tsx

Location of change: Product detail page
Description of change: Fetch product details on page using API call rather than passing all of the product details as parameters in the URL
Status: TODO
Reason for change:
Implementation notes:
Files modified:

Location of change: Product detail page
Description of change: Add loading handling while call to API is retrieving product details. Change to call product API rather than including the product info in the URL parameters should be made first
Status: TODO
Reason for change: Better user experience, gives feedback while waiting for API call to complete
Implementation notes:
Files modified:

Location of change: Product list page
Description of change: Add paging to product search results
Status: TODO
Reason for change: Will improve user experience by allowing users to more easily navigate through the list of products and keep track of their location within the search results. Currently with single page scrolling model, user progress looking through search results would be lost on refresh
Implementation notes:
Files modified:

Location of change: Product list page
Description of change: Add price-based filtering
Status: TODO
Reason for change:
Implementation notes:
Files modified:

Location of change: Product list page - search bar
Description of change: Adding debounce to search to reduce uneccesary API calls made while user is still typing
Status: TODO
Reason for change:
Implementation notes:
Files modified:

Location of change: Code base - app/page.tsx (Product List Page component)
Description of change: Refactor to break out child components of page into their own component files rather than having all of the JSX for the page returned as one big component. Will improve organization of code and ability to find and modify individual parts of the page. Break out separate components for PageTitle, ProductCard, Search, FilterControls, ProductList.
Status: TODO
Reason for change: Improve organization of code and ease of finding and modifying individual components of the product list page. 
Implementation notes:
Files modified:

