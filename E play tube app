<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>e play tube</title>
  <style>
    /* Basic style */
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      background: #f3f4f6;
      color: #1f2937;
    }
    nav {
      background: #e50914;
      color: white;
      padding: 15px 30px;
      display: flex;
      align-items: center;
      box-shadow: 0 2px 8px rgba(0,0,0,0.15);
    }
    .logo {
      font-size: 28px;
      font-weight: 700;
      letter-spacing: 3px;
      text-shadow: 0 0 4px #680202;
      display: flex;
      align-items: center;
      gap: 10px;
    }
    /* Logo icon */
    .logo svg {
      height: 40px;
      fill: white;
    }
    nav input {
      flex: 1;
      margin-left: 30px;
      padding: 8px 15px;
      border-radius: 30px;
      border: none;
      font-size: 16px;
      box-shadow: 0 0 8px rgba(255,255,255,0.7);
      outline: none;
      transition: box-shadow 0.3s;
    }
    nav input:focus {
      box-shadow: 0 0 12px #ff4500;
    }
    nav button {
      margin-left: 15px;
      padding: 10px 18px;
      background: #ff4b4b;
      border: none;
      border-radius: 25px;
      color: white;
      font-weight: 600;
      cursor: pointer;
      box-shadow: 0 3px 6px #aa1a1acc;
      transition: background 0.3s;
    }
    nav button:hover {
      background: #cc3737;
    }
    .section {
      margin: 25px 30px;
      display: flex;
      gap: 15px;
    }
    .section button {
      flex: 1;
      padding: 15px 0;
      border-radius: 10px;
      border: none;
      background: #e50914;
      color: white;
      font-size: 18px;
      font-weight: 600;
      box-shadow: 0 5px 15px #aa1a1acc;
      cursor: pointer;
      transition: background 0.3s;
    }
    .section button:hover {
      background: #cc1010;
    }
    .videos {
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
      padding: 25px 30px;
      justify-content: center;
    }
    .video-card {
      background: white;
      border-radius: 15px;
      box-shadow: 0 10px 25px -8px rgba(0,0,0,0.2);
      overflow: hidden;
      width: 320px;
      transition: transform 0.3s;
      cursor: pointer;
    }
    .video-card:hover {
      transform: scale(1.03);
      box-shadow: 0 15px 30px -8px rgba(0,0,0,0.35);
    }
    .video-card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
      border-radius: 15px 15px 0 0;
    }
    .video-card .title {
      padding: 15px;
      font-weight: 700;
      font-size: 20px;
      color: #111827;
    }
    .video-card .author {
      padding: 0 15px 15px;
      font-size: 14px;
      font-weight: 600;
      color: #6b7280;
    }
    /* Modal Styling */
    .modal {
      display: none;
      position: fixed;
      left: 0; top: 0;
      width: 100vw;
      height: 100vh;
      background: rgba(0, 0, 0, 0.5);
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }
    .modal > div {
      background: white;
      border-radius: 20px;
      padding: 30px 40px;
      min-width: 320px;
      min-height: 220px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.25);
      font-family: 'Poppins', sans-serif;
    }
    .modal h2 {
      margin-top: 0;
      margin-bottom: 15px;
      font-weight: 700;
      color: #e50914;
      letter-spacing: 1.3px;
      font-size: 28px;
    }
    .modal input[type=text],
    .modal input[type=password],
    .modal select {
      padding: 10px 12px;
      margin-bottom: 18px;
      width: 100%;
      border-radius: 12px;
      border: 1px solid #ddd;
      font-size: 16px;
      outline: none;
      transition: border-color 0.3s;
    }
    .modal input[type=text]:focus,
    .modal input[type=password]:focus,
    .modal select:focus {
      border-color: #e50914;
      box-shadow: 0 0 10px #e50914aa;
    }
    .modal button {
      width: 100%;
      padding: 12px 0;
      font-weight: 700;
      font-size: 17px;
      border-radius: 25px;
      border: none;
      background: #e50914;
      color: white;
      cursor: pointer;
      box-shadow: 0 5px 15px #aa1a1aaa;
      transition: background 0.3s;
      margin-top: 8px;
    }
    .modal button:hover {
      background: #b30e0e;
    }
    .contact-details {
      margin-top: 15px;
      font-size: 14px;
      font-weight: 600;
      letter-spacing: 0.6px;
      color: #3b3b3b;
      line-height: 1.5;
    }
    .contact-details a {
      color: #e50914;
      text-decoration: none;
      font-weight: 700;
    }
  </style>
</head>
<body>
  <nav>
    <div class="logo" title="e play tube - Video Streaming Platform">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="32" height="32"><path d="M10 15l5-3-5-3v6z"/><path fill="none" d="M0 0h24v24H0z"/></svg>
      e play tube
    </div>
    <input type="text" id="search" placeholder="Search videos..."/>
    <button onclick="openLogin()">Login</button>
    <button onclick="openProfile()">Profile</button>
  </nav>

  <div class="section">
    <button onclick="showUpload()">Upload Video</button>
    <button onclick="showShorts()">Shorts</button>
    <button onclick="showSettings()">Settings</button>
  </div>

  <div class="videos" id="videosList"></div>

  <div id="modal" class="modal"></div>

  <script>
    // Local video data (placeholder/demo)
    let videos = [
      { title: 'Welcome to e play tube', src: '', thumb: 'https://via.placeholder.com/300x180.png?text=Video', author: 'Admin', privacy: 'public' },
      { title: 'Sample Music Track', src: '', thumb: 'https://via.placeholder.com/300x180.png?text=Music', author: 'User1', privacy: 'public' }
    ];

    function renderVideos() {
      const videosList = document.getElementById('videosList');
      videosList.innerHTML = "";
      videos.forEach(video => {
        videosList.innerHTML += `
          <div class="video-card" title="${video.title}">
            <img src="${video.thumb}" alt="${video.title} thumbnail">
            <div class="title">${video.title}</div>
            <div class="author">by ${video.author}</div>
          </div>`;
      });
    }
    renderVideos();

    function openLogin() {
      showModal(`
        <h2>Login</h2>
        <input type="text" id="uname" placeholder="Username" autofocus />
        <input type="password" id="upass" placeholder="Password" />
        <button onclick="loginUser()">Login</button>
        <button onclick="closeModal()">Close</button>`);
    }
    function loginUser() {
      alert("Login successful! Welcome to e play tube.");
      closeModal();
    }

    function openProfile() {
      showModal(`
        <h2>Profile</h2>
        <p><b>Username:</b> Demo User</p>
        <p><b>Name:</b> Ajeet Kumar Patel</p>
        <p><b>Contact:</b> 9120187733</p>
        <p><b>Email:</b> <a href="mailto:patelajeetk654@zohomail.in">patelajeetk654@zohomail.in</a></p>
        <button onclick="closeModal()">Close</button>`);
    }

    function showShorts() {
      showModal(`
        <h2>Shorts</h2>
        <p>This is demo for short videos functionality.</p>
        <button onclick="closeModal()">Close</button>`);
    }

    function showSettings() {
      showModal(`
        <h2>Settings & Privacy</h2>
        <p><b>Privacy Settings</b></p>
        <select id="privacy">
          <option value="public">Public</option>
          <option value="private">Private</option>
        </select>
        <div class="contact-details">
          <p><b>Owner:</b> Ajeet Kumar Patel Patel</p>
          <p><b>Contact:</b> 9120187733</p>
          <p><b>Email:</b> <a href="mailto:patelajeetk654@zohomail.in">patelajeetk654@zohomail.in</a></p>
        </div>
        <button onclick="closeModal()">Close</button>`);
    }

    function showUpload() {
      showModal(`
        <h2>Upload Video</h2>
        <input type="text" id="vTitle" placeholder="Video Title" /><br />
        <input type="text" id="vThumb" placeholder="Thumbnail URL" /><br />
        <select id="privacy">
          <option value="public">Public</option>
          <option value="private">Private</option>
        </select><br /><br />
        <button onclick="uploadVideo()">Upload</button>
        <button onclick="closeModal()">Close</button>`);
    }

    function uploadVideo() {
      let title = document.getElementById('vTitle').value.trim();
      let thumb = document.getElementById('vThumb').value.trim();
      let privacy = document.getElementById('privacy').value;
      if (!title || !thumb) {
        alert('Please fill in all fields.');
        return;
      }
      videos.push({ title, src: '', thumb, author: 'You', privacy });
      closeModal();
      renderVideos();
    }

    function showModal(html) {
      const modal = document.getElementById('modal');
      modal.innerHTML = '<div>' + html + '</div>';
      modal.style.display = 'flex';
    }

    function closeModal() {
      const modal = document.getElementById('modal');
      modal.style.display = 'none';
    }
  </script>
</body>
</html>
