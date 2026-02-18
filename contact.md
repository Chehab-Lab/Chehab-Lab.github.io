---
layout: default
title: Contact Us
permalink: /contact/
---

<section>
  <div class="wrapper">
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 60px; margin-top: 40px;">
        <div>
            <h3 style="font-size: 1.5rem; margin-bottom: 20px;">Get in Touch</h3>
            <p style="margin-bottom: 30px;">For research collaborations, student inquiries, or general questions, please reach out via email.</p>
            
            <div style="margin-bottom: 20px;">
                <strong>Email:</strong><br>
                <a href="mailto:{{ site.email }}" style="color: var(--accent-blue); text-decoration: none;">{{ site.email }}</a>
            </div>

            <div>
                <strong>Address:</strong><br>
                American University of Beirut<br>
                Bliss Street, Hamra<br>
                Beirut, Lebanon
            </div>
        </div>
        <div style="border-radius: 24px; overflow: hidden; height: 350px; background: #eee;">
            <iframe 
                width="100%" 
                height="100%" 
                frameborder="0" 
                scrolling="no" 
                marginheight="0" 
                marginwidth="0" 
                src="https://maps.google.com/maps?q=33.8995,35.4823&z=17&output=embed"
                style="border:0; filter: grayscale(0.2) contrast(1.1);"
                allowfullscreen>
            </iframe>
        </div>
    </div>
  </div>
</section>
