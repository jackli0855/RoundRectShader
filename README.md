# RoundRectShader
To generate the rounded images I simply wrote a custom Drawable that draws a rounded rectangle using Canvas.drawRoundRect(). The trick is to use a Paint with a BitmapShader to fill the rounded rectangle with a texture instead of a simple color. Here is what the code looks like:

BitmapShader shader;
shader = new BitmapShader(bitmap, Shader.TileMode.CLAMP, Shader.TileMode.CLAMP);

Paint paint = new Paint();
paint.setAntiAlias(true);
paint.setShader(shader);

RectF rect = new RectF(0.0f, 0.0f, width, height);

// rect contains the bounds of the shape
// radius is the radius in pixels of the rounded corners
// paint contains the shader that will texture the shape
canvas.drawRoundRect(rect, radius, radius, paint);
