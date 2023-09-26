## Uploading files:
### Managing Media files
To store media files, you can create a folder in the root directory, similar to an app folder.
Media is a user-uploaded file
```python
#Same Like static files in @settings
MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
# @urls
from django.conf import settings
from django.conf.urls.static import static
if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```
### Adding Images to Products:
@models.py
```python
class ProductImage(models.Model):
    product = models.ForeignKey(Product, on_delete=models.CASCADE, related_name="images")
    image = models.ImageField(upload_to="store/products") 
#Because we use ImageField So,
# pipenv install pillow /Or python -m pip install Pillow
```
### Building an API to u=Upload Images
```python
@serializer.py
class ProductImageSerializer(serializers.ModelSerializer):
    def create(self, validated_data):
        product_id = self.context["product_id"]
        return ProductImage.objects.create(product_id=product_id, **validated_data)

    class Meta:
        model = ProductImage
        fields = ["id", "image"]
@views.py
class ProductImageViewSet(ModelViewSet):
    serializer_class = ProductImageSerializer

    def get_queryset(self):
        return ProductImage.objects.filter(product_id=self.kwargs['product_pk'])

    def get_serializer_context(self):
        return {'product_id': self.kwargs['product_pk']}
@urls.py 
products_router.register('images', views.ProductImageViewSet, basename='product-images')
```
### Returning Images from the APIs:
Add a serializer field for the desired image and connect it accordingly.
```python
images = ProductImageSerializer(many=True, read_only=True)
```
### Validation uploading File:
For other validators like (file size)
create a New file in-store app validators.py
```python
@validators.py
from django.core.exceptions import ValidationError
def validate_file_size(file):
    max_size_kb = 50
    if file.size > max_size_kb * 1024:
        raise ValidationError(f"File size must be less than {max_size_kb}KB")
@models.py
    image = models.ImageField(upload_to="store/products", validators= [validate_file_size])
```
##### Javascript basic layout to upload files.

## Enabling CORS:
Cross-Origin Resources Shairing:
- install django-cors-headers
```python
python -m pip install django-cors-headers
....
```











