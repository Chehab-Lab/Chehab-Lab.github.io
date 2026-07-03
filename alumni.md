---
layout: default
title: Alumni Registration
permalink: /alumni/
---

<section class="alumni-section">
  <div class="wrapper" style="max-width: 560px; margin: 0 auto; padding: 60px 24px;">
    <h2 style="margin-bottom: 8px;">Alumni Registration</h2>
    <p style="color: var(--text-muted, #666); margin-bottom: 40px;">Stay connected with the Chehab Lab community.</p>

    <form id="alumni-form">
      <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-bottom: 16px;">
        <div class="form-group">
          <label for="firstName">First Name</label>
          <input type="text" id="firstName" name="firstName" required placeholder="Jane">
        </div>
        <div class="form-group">
          <label for="lastName">Last Name</label>
          <input type="text" id="lastName" name="lastName" required placeholder="Doe">
        </div>
      </div>

      <div class="form-group" style="margin-bottom: 16px;">
        <label for="email">Personal Email</label>
        <input type="email" id="email" name="email" required placeholder="jane@example.com">
      </div>

      <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-bottom: 32px;">
        <div class="form-group">
          <label for="country">Country</label>
          <input type="text" id="country" name="country" required placeholder="Lebanon">
        </div>
        <div class="form-group">
          <label for="city">City</label>
          <input type="text" id="city" name="city" required placeholder="Beirut">
        </div>
      </div>

      <button type="submit" class="submit-btn">Submit</button>

      <p id="form-status" style="margin-top: 20px; text-align: center; display: none;"></p>
    </form>
  </div>
</section>

<style>
.form-group label {
  display: block;
  font-size: 0.85rem;
  font-weight: 600;
  margin-bottom: 6px;
  color: var(--text-color, #111);
}

.form-group input {
  width: 100%;
  padding: 10px 14px;
  border: 1px solid #ddd;
  border-radius: 8px;
  font-size: 1rem;
  font-family: inherit;
  background: var(--bg-light, #f9f9f9);
  transition: border-color 0.2s;
  box-sizing: border-box;
}

.form-group input:focus {
  outline: none;
  border-color: #000;
  background: #fff;
}

.submit-btn {
  width: 100%;
  padding: 12px;
  background: #000;
  color: #fff;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: background 0.2s;
}

.submit-btn:hover {
  background: #333;
}

.submit-btn:disabled {
  background: #aaa;
  cursor: not-allowed;
}
</style>

<script>
document.getElementById('alumni-form').addEventListener('submit', async function(e) {
  e.preventDefault();

  const btn = document.querySelector('.submit-btn');
  const status = document.getElementById('form-status');

  btn.disabled = true;
  btn.textContent = 'Submitting...';

  const payload = {
    firstName: document.getElementById('firstName').value.trim(),
    lastName:  document.getElementById('lastName').value.trim(),
    email:     document.getElementById('email').value.trim(),
    country:   document.getElementById('country').value.trim(),
    city:      document.getElementById('city').value.trim()
  };

  try {
    await fetch('https://script.google.com/macros/s/AKfycbwdOVY6-AhLH5Cz8vqYMPBgqwMI2G1uTivzpujaKwT4vm2nbPPivUx7h7tyGqHVLTGr/exec', {
      method: 'POST',
      mode: 'no-cors',
      body: JSON.stringify(payload)
    });

    status.style.display = 'block';
    status.style.color = 'green';
    status.textContent = 'Thank you! Your information has been recorded.';
    this.reset();
  } catch (err) {
    status.style.display = 'block';
    status.style.color = 'red';
    status.textContent = 'Something went wrong. Please try again.';
  } finally {
    btn.disabled = false;
    btn.textContent = 'Submit';
  }
});
</script>
