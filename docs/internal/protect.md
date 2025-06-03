<script>
  const correctPassword = "acadia!!12";
  const urlPw = new URLSearchParams(window.location.search).get("pw");
  const unlocked = sessionStorage.getItem("accessGranted");

  if (!unlocked) {
    if (urlPw === correctPassword) {
      sessionStorage.setItem("accessGranted", "true");
    } else {
      const entered = prompt("🔐 Enter internal access password:");
      if (entered === correctPassword) {
        sessionStorage.setItem("accessGranted", "true");
      } else {
        document.body.innerHTML = "<h1 style='margin:2rem;font-family:sans-serif;'>🚫 Unauthorized</h1>";
        throw new Error("Unauthorized");
      }
    }
  }
</script>
