# Blogging-platform-
<html>
    <head>
        <title>Mini Blog</title>
        <style>
            body {font-family: Arial; background: #101827; color: #e4e4e7; margin: 40px;}
            a {color: #67e8f9; text-decoration: none;}
            .post {background: #1e293b; padding: 15px; border-radius: 10px; margin-bottom: 15px;}
            .btn {background: #67e8f9; color: black; padding: 6px 12px; border-radius: 6px;}
        </style>
    </head>
    <body>
        <h1>📝 Mini Blogging Platform</h1>
        <a href="{{ url_for('create_post') }}" class="btn">New Post</a>
        <hr>
        {% for post in posts %}
        <div class="post">
            <h2>{{ post['title'] }}</h2>
            <p>{{ post['content'][:200] }}...</p>
            <a href="{{ url_for('view_post', index=loop.index0) }}">Read More</a>
        </div>
        {% else %}
        <p>No posts yet. <a href="{{ url_for('create_post') }}">Create one</a>!</p>
        {% endfor %}
    </body>
    </html>
    
    <html>
    <head><title>{{ post['title'] }}</title></head>
    <body style="font-family: Arial; background: #0f172a; color: #f8fafc; margin: 40px;">
        <h1>{{ post['title'] }}</h1>
        <p>{{ post['content'] }}</p>
        <a href="/">← Back</a>
    </body>
    </html>
    


    
    
    <html>
    <head>
        <title>Create Post</title>
        <style>
            body {font-family: Arial; background: #0f172a; color: #f8fafc; margin: 40px;}
            input, textarea {width: 100%; padding: 10px; margin-top: 8px; border-radius: 6px; border: none;}
            textarea {height: 200px;}
            .btn {background: #67e8f9; color: black; padding: 8px 14px; border-radius: 6px; margin-top: 8px;}
        </style>
    </head>
    <body>
        <h1>New Post</h1>
        <form method="post">
            <input name="title" placeholder="Post title" required><br>
            <textarea name="content" placeholder="Write your content here..." required></textarea><br>
            <button type="submit" class="btn">Publish</button>
        </form>
        <a href="/">← Back</a>
    </body>
    </html>
