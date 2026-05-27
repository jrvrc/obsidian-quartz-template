---
title: Interactive Mind Map
---

<script>
function triggerGlobalGraph() {
  if (document.body.dataset.slug === "graph") {
    let attempts = 0;
    
    const interval = setInterval(() => {
      const globalGraphBtn = document.querySelector(".global-graph-icon");
      const globalGraphOuter = document.querySelector(".global-graph-outer");
      
      if (globalGraphBtn) {
        // Try clicking the button
        globalGraphBtn.click();
        
        // Check if the global graph successfully activated (it gets an "active" class)
        if (globalGraphOuter && globalGraphOuter.classList.contains("active")) {
          clearInterval(interval); // Success! Stop clicking.
        }
      }
      
      attempts++;
      // Stop trying after 5 seconds to prevent an infinite loop if something goes wrong
      if (attempts > 50) { 
        clearInterval(interval);
      }
    }, 100); // Check every 100 milliseconds
  }
}

// Run immediately if this is the first page loaded
triggerGlobalGraph();

// Run on navigation (whenever you click a link inside your site)
document.addEventListener("nav", triggerGlobalGraph);
</script>
