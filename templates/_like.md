=============== 좋아요
======= models.py

class Comment(models.Model):
objects = models.Manager()
content = models.TextField()
user = models.ForeignKey(User, on_delete = models.CASCADE)
post = models.ForeignKey(Post, on_delete = models.CASCADE, related_name='comments')
# Post의 Comment, Comment의 Post를 서로 추적 가능

created_at = models.DateTimeField(auto_now_add=True)


======= 터미널

python manage.py makemigrations
python manage.py migrate