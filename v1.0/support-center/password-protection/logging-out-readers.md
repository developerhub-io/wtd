---
type: page
title: Logging Out Readers
listed: true
slug: logging-out-readers
description: 
index_title: Logging Out Readers
hidden: 
keywords: 
tags: 
---

To log out readers, you can invoke the `logout` function on the `window` object. This action effectively terminates the current session, ensuring that users are securely logged out of the application.

To let users log out from a secure session, you can add a logout button in the top right corner near the navigation links. Include this [Custom JS](/support-center/custom-javascript):

{% code %}
{% tab language="html" %}
<script>
  document.addEventListener('onprojectloaded', function () {
    var logoutBtn = document.createElement('DIV');
    logoutBtn.innerHTML = 'Logout';
    logoutBtn.classList.add('logout'); // Style as needed
    logoutBtn.onclick = function() {
      window.logout();
      window.location.href = '/'; // Change this to a useful link
    };
    document.querySelector('.links-container').appendChild(logoutBtn);
  });
</script>
{% /tab %}
{% /code %}