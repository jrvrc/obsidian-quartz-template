---
title: Interactive Mind Map
---

<script>
function triggerGlobalGraph() {
  // Only trigger if we are currently on the /graph page
  if (document.body.dataset.slug === "graph") {
    // A tiny delay ensures Quartz has finished rendering its components first
    setTimeout(() => {
      const globalGraphBtn = document.querySelector(".global-graph-icon");
      if (globalGraphBtn) {
        globalGraphBtn.click();
      }
    }, 150);
  }
}

// Run immediately if this is the first page loaded
triggerGlobalGraph();

// Run on navigation (whenever you click a link inside your site)
document.addEventListener("nav", triggerGlobalGraph);
</script>
