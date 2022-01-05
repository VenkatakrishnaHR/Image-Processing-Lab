<div class="cell code" id="OqcFFWFJiJ5t">

``` python
import cv2
from google.colab.patches import cv2_imshow
```

</div>

<div class="cell markdown" id="UE2wBCaSjNke">

Show Image

</div>

<div class="cell code" data-colab="{&quot;height&quot;:224,&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}" id="YCQz48YvI9Bl" data-outputId="72b6bd7f-dba7-485d-8513-6fc6854bdb0a">

``` python
img = cv2.imread("image.jpeg", -1)
cv2_imshow(img)
```

<div class="output display_data">

![](2c68d86123ea52ed3e9f28279fa2efd124cc4b75.png)

</div>

</div>

<div class="cell code" data-colab="{&quot;height&quot;:224,&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}" id="pXegoLC72D0A" data-outputId="4774e6ad-d3cf-4084-c503-f5cc72938c7e">

``` python
#Here, 0 indicates gray scale level
img = cv2.imread("image.jpeg", 0)
cv2_imshow(img)
```

<div class="output display_data">

![](14384834070d9773f3de524460490e9f9adb3166.png)

</div>

</div>

<div class="cell code" data-colab="{&quot;height&quot;:241,&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}" id="ycDssmlZ11gc" data-outputId="65fb407c-0656-40b0-d204-c55b0f585a85">

``` python
img = cv2.imread('image.jpeg')
print(type(img))

# cv2.imshow(img)
cv2_imshow(img)
```

<div class="output stream stdout">

    <class 'numpy.ndarray'>

</div>

<div class="output display_data">

![](2c68d86123ea52ed3e9f28279fa2efd124cc4b75.png)

</div>

</div>

<div class="cell markdown" id="xrm9eN91hae6">

Negative image

</div>

<div class="cell code" data-colab="{&quot;height&quot;:224,&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}" id="HphLv-RrhW0z" data-outputId="9f68ef35-3ef7-4d0b-e5fd-191b5a3a6d04">

``` python
img = cv2.imread("image.jpeg")
negativeImg = img.copy()
negativeImg[:,:,0] = 255 - negativeImg[:,:,0]
negativeImg[:,:,1] = 255 - negativeImg[:,:,1]
negativeImg[:,:,2] = 255 - negativeImg[:,:,2]
cv2_imshow( negativeImg )
```

<div class="output display_data">

![](a2278af7196b93e284b30e058455faf07cb8ccda.png)

</div>

</div>

<div class="cell code" data-colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}" id="8WSaunYMj2fQ" data-outputId="16968eaa-efa2-46c2-8a64-5c3cb9111c56">

``` python
img.shape
```

<div class="output execute_result" data-execution_count="5">

    (207, 244, 3)

</div>

</div>

<div class="cell code" data-colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}" id="zXhcKl6fLd0i" data-outputId="ed51247a-6ca0-4f68-ccd5-823ecc960163">

``` python
img.size
```

<div class="output execute_result" data-execution_count="6">

    151524

</div>

</div>

<div class="cell code" data-colab="{&quot;height&quot;:638,&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}" id="p1Hhn5K8MqQS" data-outputId="094954a3-19d2-4446-cb44-0c76144ed9e2">

``` python
blue = img[:,:,0]
cv2_imshow(blue)
green = img[:,:,1]
cv2_imshow(green)
red = img[:,:,2]
cv2_imshow(red)
```

<div class="output display_data">

![](7636bac6a1a3d30cfaefc2f76155851cd06a877a.png)

</div>

<div class="output display_data">

![](d0a0bf152c355811d86109c23e28c37f525ba608.png)

</div>

<div class="output display_data">

![](6a390d6db604c7b9d4f422dd01681f2b08b64c31.png)

</div>

</div>

<div class="cell code" data-colab="{&quot;height&quot;:638,&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}" id="GBSkmimLNjEK" data-outputId="d5dd282c-2a0a-4003-d3c8-ed013d4ce389">

``` python
blueImg = img.copy()
blueImg[:,:,1] = 0
blueImg[:,:,2] = 0
cv2_imshow( blueImg )

redImg = img.copy()
redImg[:,:,0] = 0
redImg[:,:,1] = 0
cv2_imshow( redImg )

greenImg = img.copy()
greenImg[:,:,0] = 0
greenImg[:,:,2] = 0
cv2_imshow( greenImg )
```

<div class="output display_data">

![](6cb94014b707318a4f2cf169b0681061dad64525.png)

</div>

<div class="output display_data">

![](3a683a8a7725f07bfc1ba823eea08940d251ed59.png)

</div>

<div class="output display_data">

![](ad7fccc327958d26aabb4c0c853332a71f96cadd.png)

</div>

</div>

<div class="cell code" data-colab="{&quot;height&quot;:845,&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}" id="lMnLnP_LOHLy" data-outputId="362e43c8-6c6c-450e-ffa3-3c5f351653c4">

``` python
b, g, r = cv2.split(img)
cv2_imshow( img )
cv2_imshow( r )
cv2_imshow( g )
cv2_imshow( b )
```

<div class="output display_data">

![](2c68d86123ea52ed3e9f28279fa2efd124cc4b75.png)

</div>

<div class="output display_data">

![](6a390d6db604c7b9d4f422dd01681f2b08b64c31.png)

</div>

<div class="output display_data">

![](d0a0bf152c355811d86109c23e28c37f525ba608.png)

</div>

<div class="output display_data">

![](7636bac6a1a3d30cfaefc2f76155851cd06a877a.png)

</div>

</div>

<div class="cell code" data-colab="{&quot;height&quot;:827,&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}" id="Dd1wFY50PJPp" data-outputId="cce04060-c69e-4e01-c375-09989ce1985a">

``` python
img = cv2.imread("images.jpeg")
img2 = cv2.imread("images.jpeg", 0)
# img = cv2.imread("download.png")
# img2 = cv2.imread("download (1).png", 0)
negativeImg = img.copy()
negativeImg[:,:,0] = 255 - negativeImg[:,:,0]
negativeImg[:,:,1] = 255 - negativeImg[:,:,1]
negativeImg[:,:,2] = 255 - negativeImg[:,:,2]
cv2_imshow( negativeImg )

negativeImg = img2.copy()
negativeImg[:,:] = 255 - negativeImg[:,:]
cv2_imshow( negativeImg )
```

<div class="output display_data">

![](2b5677b189018a1f7fcec6e29c5dc76768e37b22.png)

</div>

<div class="output display_data">

![](17737f931cb28d17a39af94853900db6dfa82264.png)

</div>

</div>
