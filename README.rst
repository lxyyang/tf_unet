#在运行demo时，增加layers时，输出的结果尺寸和原图差距较大，因此做了如下修改（未在上面代码中进行修改）：
1、将卷积操作的padding改为‘same’
2、修改/tf_unet/util.py中‘crop_to_shape()函数’：
   def crop_to_shape(data, shape):
   	...
	...
	return data[0:, offset0:(-offset0 + data.shape[1]), offset1:(-offset1 + data.shape[2])]
