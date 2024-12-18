# bieumaugioithieu.github.io
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Biểu mẫu Giới thiệu bản thân</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .container {
            width: 80%;
            margin: 0 auto;
        }
        .form-section {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 8px;
        }
        input, select, textarea {
            width: 100%;
            padding: 8px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .form-group {
            margin-bottom: 20px;
        }
        .profile-img {
            max-width: 150px;
            margin-bottom: 20px;
        }
        .audio-player, .video-player {
            width: 100%;
            margin-bottom: 20px;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Giới thiệu bản thân</h1>
    
    <form action="#" method="post">
        <!-- Họ tên -->
        <div class="form-section">
            <label for="full-name">Họ và tên:</label>
            <input type="text" id="full-name" name="full_name" required>
        </div>
        
        <!-- Ngày tháng năm sinh -->
        <div class="form-section">
            <label for="dob">Ngày tháng năm sinh:</label>
            <input type="date" id="dob" name="dob" required>
        </div>

        <!-- Giới tính -->
        <div class="form-section">
            <label for="gender">Giới tính:</label>
            <select id="gender" name="gender" required>
                <option value="Nam">Nam</option>
                <option value="Nữ">Nữ</option>
                <option value="Khác">Khác</option>
            </select>
        </div>

        <!-- Địa chỉ -->
        <div class="form-section">
            <label for="address">Địa chỉ:</label>
            <input type="text" id="address" name="address" required>
        </div>

        <!-- Trường học -->
        <div class="form-section">
            <label for="school">Trường học:</label>
            <input type="text" id="school" name="school" required>
        </div>

        <!-- Lớp -->
        <div class="form-section">
            <label for="class">Lớp:</label>
            <input type="text" id="class" name="class" required>
        </div>

        <!-- Sở thích -->
        <div class="form-section">
            <label for="hobbies">Sở thích:</label>
            <textarea id="hobbies" name="hobbies" rows="4" required></textarea>
        </div>

        <!-- Nghề nghiệp tương lai -->
        <div class="form-section">
            <label for="future-job">Nghề nghiệp tương lai:</label>
            <input type="text" id="future-job" name="future_job" required>
        </div>

        <!-- Ảnh đại diện -->
        <div class="form-section">
            <label for="profile-img">Ảnh đại diện:</label>
            <input type="file" id="profile-img" name="profile_img" accept="image/*" required>
            <img id="profile-preview" class="profile-img" src="#" alt="Ảnh đại diện" style="display:none;">
        </div>

        <!-- Bài hát yêu thích -->
        <div class="form-section">
            <label for="favorite-song">Bài hát yêu thích:</label>
            <input type="file" id="favorite-song" name="favorite_song" accept="audio/*" required>
            <audio id="audio-player" class="audio-player" controls>
                <source src="#" type="audio/mp3">
                Trình duyệt của bạn không hỗ trợ thẻ audio.
            </audio>
        </div>

        <!-- Video giới thiệu bản thân -->
        <div class="form-section">
            <label for="intro-video">Video giới thiệu bản thân:</label>
            <input type="file" id="intro-video" name="intro_video" accept="video/*" required>
            <video id="video-player" class="video-player" controls>
                <source src="#" type="video/mp4">
                Trình duyệt của bạn không hỗ trợ thẻ video.
            </video>
        </div>

        <button type="submit">Gửi</button>
    </form>
</div>

<script>
    // Hiển thị ảnh đại diện khi người dùng chọn file ảnh
    document.getElementById("profile-img").addEventListener("change", function(event) {
        const file = event.target.files[0];
        if (file) {
            const reader = new FileReader();
            reader.onload = function(e) {
                const img = document.getElementById("profile-preview");
                img.src = e.target.result;
                img.style.display = "block";
            };
            reader.readAsDataURL(file);
        }
    });

    // Hiển thị bài hát yêu thích khi người dùng chọn file âm thanh
    document.getElementById("favorite-song").addEventListener("change", function(event) {
        const file = event.target.files[0];
        const audioPlayer = document.getElementById("audio-player");
        const source = audioPlayer.querySelector("source");

        if (file) {
            const fileURL = URL.createObjectURL(file);
            source.src = fileURL;
            audioPlayer.load();  // Tải lại audio
        }
    });

    // Hiển thị video giới thiệu bản thân khi người dùng chọn file video
    document.getElementById("intro-video").addEventListener("change", function(event) {
        const file = event.target.files[0];
        const videoPlayer = document.getElementById("video-player");
        const source = videoPlayer.querySelector("source");

        if (file) {
            const fileURL = URL.createObjectURL(file);
            source.src = fileURL;
            videoPlayer.load();  // Tải lại video
        }
    });
</script>

</body>
</html>
