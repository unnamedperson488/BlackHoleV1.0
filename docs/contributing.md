---
layout: default
title: Contributing
---

<div class="hero fade-in">
  <h1>Contributing</h1>
  <p>Guidelines for contributing to the Black Hole V1.0 project and community.</p>
</div>

<section class="fade-in">
  <h2 class="section-title">Ways to Contribute</h2>
  
  <div class="features-grid">
    <div class="feature-card">
      <div class="feature-icon"><i class="fas fa-code"></i></div>
      <h3 class="feature-title">Code Contributions</h3>
      <p class="feature-description">Help improve the firmware, web interface, or mobile applications by submitting code changes.</p>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fas fa-bug"></i></div>
      <h3 class="feature-title">Bug Reports</h3>
      <p class="feature-description">Report bugs or issues you encounter to help us improve the product for everyone.</p>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fas fa-lightbulb"></i></div>
      <h3 class="feature-title">Feature Requests</h3>
      <p class="feature-description">Suggest new features or improvements to existing functionality.</p>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fas fa-book"></i></div>
      <h3 class="feature-title">Documentation</h3>
      <p class="feature-description">Help improve our documentation with corrections, clarifications, or translations.</p>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fas fa-users"></i></div>
      <h3 class="feature-title">Community Support</h3>
      <p class="feature-description">Help other users by answering questions in our community forums and Discord server.</p>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fas fa-microchip"></i></div>
      <h3 class="feature-title">Hardware Mods</h3>
      <p class="feature-description">Share your hardware modifications, custom cases, or antenna designs with the community.</p>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">GitHub Repositories</h2>
  
  <div class="faq-item">
    <p class="faq-question">Main Repositories</p>
    <div class="faq-answer">
      <p>Our project is divided into several repositories on GitHub:</p>
      
      <ul>
        <li><a href="https://github.com/blackhole/firmware">blackhole/firmware</a> - Core firmware for the Black Hole device</li>
        <li><a href="https://github.com/blackhole/web-interface">blackhole/web-interface</a> - Web interface for controlling the device</li>
        <li><a href="https://github.com/blackhole/mobile-apps">blackhole/mobile-apps</a> - Android and iOS applications</li>
        <li><a href="https://github.com/blackhole/hardware">blackhole/hardware</a> - Hardware design files and schematics</li>
        <li><a href="https://github.com/blackhole/documentation">blackhole/documentation</a> - Documentation and user guides</li>
      </ul>
      
      <p>Each repository has its own specific contribution guidelines, but the general principles outlined here apply to all.</p>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Code Contribution Guidelines</h2>
  
  <div class="faq-item">
    <p class="faq-question">Getting Started</p>
    <div class="faq-answer">
      <ol>
        <li><strong>Fork the repository</strong> you want to contribute to</li>
        <li><strong>Clone your fork</strong> to your local machine</li>
        <li><strong>Create a new branch</strong> for your feature or bugfix</li>
        <li><strong>Make your changes</strong>, following our coding standards</li>
        <li><strong>Test your changes</strong> thoroughly</li>
        <li><strong>Commit your changes</strong> with clear, descriptive commit messages</li>
        <li><strong>Push your branch</strong> to your fork on GitHub</li>
        <li><strong>Submit a pull request</strong> to the original repository</li>
      </ol>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Coding Standards</p>
    <div class="faq-answer">
      <p>We follow these coding standards across our projects:</p>
      
      <h4>C/C++ (Firmware)</h4>
      <ul>
        <li>Follow the <a href="https://www.kernel.org/doc/html/latest/process/coding-style.html">Linux kernel coding style</a> with 4-space indentation</li>
        <li>Use descriptive variable and function names</li>
        <li>Comment complex algorithms and non-obvious code</li>
        <li>Keep functions small and focused on a single task</li>
        <li>Include appropriate error handling</li>
      </ul>
      
      <h4>JavaScript (Web Interface)</h4>
      <ul>
        <li>Follow the <a href="https://github.com/airbnb/javascript">Airbnb JavaScript Style Guide</a></li>
        <li>Use ES6+ features where appropriate</li>
        <li>Document functions with JSDoc comments</li>
        <li>Use meaningful variable and function names</li>
      </ul>
      
      <h4>General Guidelines</h4>
      <ul>
        <li>Write clear, descriptive commit messages</li>
        <li>Keep pull requests focused on a single feature or bugfix</li>
        <li>Include tests for new features or bugfixes</li>
        <li>Update documentation to reflect your changes</li>
      </ul>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Pull Request Process</p>
    <div class="faq-answer">
      <ol>
        <li>Ensure your code follows our coding standards</li>
        <li>Update the documentation to reflect any changes</li>
        <li>Include tests that verify your changes</li>
        <li>Ensure all tests pass before submitting</li>
        <li>Fill out the pull request template completely</li>
        <li>Be responsive to feedback and be willing to make changes</li>
      </ol>
      
      <p>Pull requests will be reviewed by maintainers, who may request changes before merging. Please be patient and responsive during this process.</p>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Bug Reports and Feature Requests</h2>
  
  <div class="faq-item">
    <p class="faq-question">Reporting Bugs</p>
    <div class="faq-answer">
      <p>When reporting a bug, please include:</p>
      
      <ul>
        <li><strong>Device Information:</strong> Firmware version, hardware revision, etc.</li>
        <li><strong>Steps to Reproduce:</strong> Detailed steps to reproduce the issue</li>
        <li><strong>Expected Behavior:</strong> What you expected to happen</li>
        <li><strong>Actual Behavior:</strong> What actually happened</li>
        <li><strong>Screenshots or Logs:</strong> If applicable</li>
        <li><strong>Additional Context:</strong> Any other relevant information</li>
      </ul>
      
      <p>Please use the issue tracker in the appropriate GitHub repository to report bugs.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Suggesting Features</p>
    <div class="faq-answer">
      <p>When suggesting a feature, please include:</p>
      
      <ul>
        <li><strong>Clear Description:</strong> What the feature should do</li>
        <li><strong>Use Case:</strong> Why this feature would be useful</li>
        <li><strong>Alternatives:</strong> Any alternative solutions you've considered</li>
        <li><strong>Additional Context:</strong> Any other relevant information</li>
      </ul>
      
      <p>Feature requests should be submitted to the issue tracker in the appropriate GitHub repository, using the feature request template.</p>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Documentation Contributions</h2>
  
  <div class="faq-item">
    <p class="faq-question">Improving Documentation</p>
    <div class="faq-answer">
      <p>Our documentation is stored in the <a href="https://github.com/blackhole/documentation">blackhole/documentation</a> repository. To contribute:</p>
      
      <ol>
        <li>Fork and clone the repository</li>
        <li>Make your changes to the relevant Markdown files</li>
        <li>Submit a pull request with a clear description of your changes</li>
      </ol>
      
      <p>Documentation improvements might include:</p>
      <ul>
        <li>Fixing typos or grammatical errors</li>
        <li>Clarifying confusing instructions</li>
        <li>Adding missing information</li>
        <li>Creating new tutorials or guides</li>
        <li>Translating documentation to other languages</li>
      </ul>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Community Guidelines</h2>
  
  <div class="faq-item">
    <p class="faq-question">Code of Conduct</p>
    <div class="faq-answer">
      <p>We are committed to providing a welcoming and inclusive environment for all contributors. We expect all participants to adhere to our Code of Conduct, which includes:</p>
      
      <ul>
        <li>Being respectful and considerate of others</li>
        <li>Using inclusive language</li>
        <li>Being open to constructive criticism</li>
        <li>Focusing on what is best for the community</li>
        <li>Showing empathy towards other community members</li>
      </ul>
      
      <p>Unacceptable behavior includes:</p>
      <ul>
        <li>Harassment or discrimination of any kind</li>
        <li>Offensive comments or personal attacks</li>
        <li>Trolling, insulting/derogatory comments, or personal/political attacks</li>
        <li>Public or private harassment</li>
        <li>Publishing others' private information without permission</li>
        <li>Other conduct which could reasonably be considered inappropriate</li>
      </ul>
      
      <p>Violations of the Code of Conduct may result in temporary or permanent bans from our community spaces.</p>
    </div>
  </div>
</section>

<div class="faq-item fade-in mt-5">
  <p class="faq-question">Recognition</p>
  <div class="faq-answer">
    <p>We value all contributions to the Black Hole project. Contributors will be recognized in the following ways:</p>
    
    <ul>
      <li>All code contributors will be listed in the CONTRIBUTORS.md file in each repository</li>
      <li>Significant contributions may be highlighted in release notes</li>
      <li>Regular contributors may be invited to join the core team</li>
    </ul>
    
    <p>Thank you for considering contributing to the Black Hole project. Your contributions help make this project better for everyone!</p>
  </div>
</div>

<div class="btn-group mt-5 fade-in">
  <a href="https://github.com/blackhole" class="btn">GitHub Repositories</a>
  <a href="https://discord.gg/" class="btn btn-secondary">Join Discord Community</a>
</div>
