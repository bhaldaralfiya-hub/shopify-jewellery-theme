**How you loaded and separated featured vs nonfeatured products**

Shopify products can have tags.
I have added the "featured" tag to some products.

When the collection page loads, we check each product:

If the product has the featured tag → move it to the top
Other products → show after featured products

Using JavaScript, the products are arranged like this:

Featured products first and then Normal products after

-----------------------------------------------------------------------------------------------------------
**How infinite scroll was implemented**

Instead of loading all products at once,I first show a small set of products on the page.
Then, as the user scrolls down:
The browser checks when the user reaches near the bottom of the product list
Automatically, the next set of products gets loaded
This continues until all products are shown
I used an invisible element at the bottom of the grid and IntersectionObserver to detect scrolling.
Products start loading a little before reaching the bottom, so scrolling feels smooth without waiting.

------------------------------------------------------------------------------------------------------------
**How duplicate products were prevented**

To prevent duplicate products:

I stored the IDs of products already displayed
Before showing a product, check:
If product is already shown → skip it
If not shown → display it and save its ID

---------------------------------------------------------------------------------------------------------
**How filtering and sorting were handled while maintaining proper logic**

I used both Liquid and JavaScript for this feature.

Liquid checks whether filters or custom sorting are active and passes a simple true/false value to the page.
JavaScript reads that value:
If it’s the default view → run featured products + infinite scroll logic
If filters/sorting are active → do nothing and let Shopify handle everything normally

------------------------------------------------------------------------------------------------
