test example


curl -LO https://github.com/tensorflow/tensorflow/raw/master/tensorflow/examples/label_image/label_image.py
python label_image.py \
--graph=/tmp/output_graph.pb --labels=/tmp/output_labels.txt \
--input_layer=Placeholder \
--output_layer=final_result \
--image=/Users/valquiria/Desktop/spiral\ galaxy.jpg 

![Image of spiral]
(https://github.com/Regulus239/EC601-TensorFlow-Practice/blob/master/spriral%20galaxy.jpg)
result
spiral galaxy 0.99998486
elliptical galaxy 1.5191506e-05


python label_image.py \
--graph=/tmp/output_graph.pb --labels=/tmp/output_labels.txt \
--input_layer=Placeholder \
--output_layer=final_result \
--image=/Users/valquiria/Desktop/elliptical\ galaxy.jpg


![Image of spiral!]
(https://github.com/Regulus239/EC601-TensorFlow-Practice/blob/master/elliptical%20galaxy.jpg)


result
elliptical galaxy 0.9489488
spiral galaxy 0.051051147
