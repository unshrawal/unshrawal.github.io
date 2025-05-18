---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<div id="typing-content">
I am a rising senior at UT Austin, majoring in computer science. I am strongly interested in computing systems and have over 3 years of experience designing projects from the ground up.
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  // Target the content area with our specific ID
  const contentArea = document.getElementById('typing-content');
  
  if (contentArea) {
    // Store the original content
    const originalContent = contentArea.innerHTML;
    
    // Clear the content initially
    contentArea.innerHTML = '';
    
    // Create a container for the typing effect with a blinking cursor
    const typingContainer = document.createElement('div');
    typingContainer.className = 'typing-effect';
    typingContainer.innerHTML = '<span class="typed-text"></span><span class="cursor">|</span>';
    contentArea.appendChild(typingContainer);
    
    const typedTextSpan = typingContainer.querySelector('.typed-text');
    const cursorSpan = typingContainer.querySelector('.cursor');
    
    // Convert HTML to plain text for typing (removing HTML tags)
    const textToType = originalContent.trim().replace(/<[^>]*>/g, '');
    
    let charIndex = 0;
    const typingDelay = 50; // Delay between each character (in ms)
    
    function type() {
      if (charIndex < textToType.length) {
        // Add next character
        typedTextSpan.textContent += textToType.charAt(charIndex);
        charIndex++;
        setTimeout(type, typingDelay);
      }
    }
    
    // Start the typing effect with a short delay
    setTimeout(type, 1000);
  }
});
</script>

<style>
.cursor {
  display: inline-block;
  width: 3px;
  margin-left: 2px;
  animation: blink 1s infinite;
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}
</style>