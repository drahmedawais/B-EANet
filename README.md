# B-EANet
\begin{table}[h!]
\centering
\begin{tabular}{|l|l|l|l|r|}
\hline
Layer Name & Layer Type & Input Shape & Output Shape & Parameters \\
\hline
input_1 & InputLayer & [(None, 224, 224, 3)] & [(None, 224, 224, 3)] & 0.0 \\
\hline
data_augmentation & Sequential & (None, 224, 224, 3) & (None, 224, 224, 3) & 7.0 \\
\hline
patch_extract & PatchExtract & (None, 224, 224, 3) & (None, 324, 432) & 0.0 \\
\hline
patch_embedding & PatchEmbedding & (None, 324, 432) & (None, 324, 64) & 48448 \\
\hline
layer_normalization & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_1 & Dense & (None, 324, 64) & (None, 324, 256) & 16384 \\
\hline
tf.reshape & TFOpLambda & (None, 324, 256) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.compat.v1.transpose & TFOpLambda & (None, 324, 16, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_2 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
softmax & Softmax & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
tf.math.reduce_sum & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 1) & 0.0 \\
\hline
tf.__operators__.add & TFOpLambda & () & (None, 16, 324, 1) & 0.0 \\
\hline
tf.math.truediv & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dropout & Dropout & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_3 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
tf.compat.v1.transpose_1 & TFOpLambda & (None, 16, 324, 16) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.reshape_1 & TFOpLambda & (None, 324, 16, 16) & (None, 324, 256) & 0.0 \\
\hline
dense_4 & Dense & (None, 324, 256) & (None, 324, 64) & 16384 \\
\hline
dropout_1 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_1 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_5 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_2 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
dense_6 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_3 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_1 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_2 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_7 & Dense & (None, 324, 64) & (None, 324, 256) & 16384 \\
\hline
tf.reshape_2 & TFOpLambda & (None, 324, 256) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.compat.v1.transpose_2 & TFOpLambda & (None, 324, 16, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_8 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
softmax_1 & Softmax & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
tf.math.reduce_sum_1 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 1) & 0.0 \\
\hline
tf.__operators__.add_1 & TFOpLambda & () & (None, 16, 324, 1) & 0.0 \\
\hline
tf.math.truediv_1 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dropout_4 & Dropout & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_9 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
tf.compat.v1.transpose_3 & TFOpLambda & (None, 16, 324, 16) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.reshape_3 & TFOpLambda & (None, 324, 16, 16) & (None, 324, 256) & 0.0 \\
\hline
dense_10 & Dense & (None, 324, 256) & (None, 324, 64) & 16384 \\
\hline
dropout_5 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_2 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_3 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_11 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_6 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
dense_12 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_7 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_3 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_4 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_13 & Dense & (None, 324, 64) & (None, 324, 256) & 16384 \\
\hline
tf.reshape_4 & TFOpLambda & (None, 324, 256) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.compat.v1.transpose_4 & TFOpLambda & (None, 324, 16, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_14 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
softmax_2 & Softmax & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
tf.math.reduce_sum_2 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 1) & 0.0 \\
\hline
tf.__operators__.add_2 & TFOpLambda & () & (None, 16, 324, 1) & 0.0 \\
\hline
tf.math.truediv_2 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dropout_8 & Dropout & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_15 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
tf.compat.v1.transpose_5 & TFOpLambda & (None, 16, 324, 16) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.reshape_5 & TFOpLambda & (None, 324, 16, 16) & (None, 324, 256) & 0.0 \\
\hline
dense_16 & Dense & (None, 324, 256) & (None, 324, 64) & 16384 \\
\hline
dropout_9 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_4 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_5 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_17 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_10 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
dense_18 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_11 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_5 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_6 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_19 & Dense & (None, 324, 64) & (None, 324, 256) & 16384 \\
\hline
tf.reshape_6 & TFOpLambda & (None, 324, 256) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.compat.v1.transpose_6 & TFOpLambda & (None, 324, 16, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_20 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
softmax_3 & Softmax & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
tf.math.reduce_sum_3 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 1) & 0.0 \\
\hline
tf.__operators__.add_3 & TFOpLambda & () & (None, 16, 324, 1) & 0.0 \\
\hline
tf.math.truediv_3 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dropout_12 & Dropout & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_21 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
tf.compat.v1.transpose_7 & TFOpLambda & (None, 16, 324, 16) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.reshape_7 & TFOpLambda & (None, 324, 16, 16) & (None, 324, 256) & 0.0 \\
\hline
dense_22 & Dense & (None, 324, 256) & (None, 324, 64) & 16384 \\
\hline
dropout_13 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_6 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_7 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_23 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_14 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
dense_24 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_15 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_7 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_8 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_25 & Dense & (None, 324, 64) & (None, 324, 256) & 16384 \\
\hline
tf.reshape_8 & TFOpLambda & (None, 324, 256) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.compat.v1.transpose_8 & TFOpLambda & (None, 324, 16, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_26 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
softmax_4 & Softmax & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
tf.math.reduce_sum_4 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 1) & 0.0 \\
\hline
tf.__operators__.add_4 & TFOpLambda & () & (None, 16, 324, 1) & 0.0 \\
\hline
tf.math.truediv_4 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dropout_16 & Dropout & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_27 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
tf.compat.v1.transpose_9 & TFOpLambda & (None, 16, 324, 16) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.reshape_9 & TFOpLambda & (None, 324, 16, 16) & (None, 324, 256) & 0.0 \\
\hline
dense_28 & Dense & (None, 324, 256) & (None, 324, 64) & 16384 \\
\hline
dropout_17 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_8 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_9 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_29 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_18 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
dense_30 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_19 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_9 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_10 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_31 & Dense & (None, 324, 64) & (None, 324, 256) & 16384 \\
\hline
tf.reshape_10 & TFOpLambda & (None, 324, 256) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.compat.v1.transpose_10 & TFOpLambda & (None, 324, 16, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_32 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
softmax_5 & Softmax & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
tf.math.reduce_sum_5 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 1) & 0.0 \\
\hline
tf.__operators__.add_5 & TFOpLambda & () & (None, 16, 324, 1) & 0.0 \\
\hline
tf.math.truediv_5 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dropout_20 & Dropout & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_33 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
tf.compat.v1.transpose_11 & TFOpLambda & (None, 16, 324, 16) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.reshape_11 & TFOpLambda & (None, 324, 16, 16) & (None, 324, 256) & 0.0 \\
\hline
dense_34 & Dense & (None, 324, 256) & (None, 324, 64) & 16384 \\
\hline
dropout_21 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_10 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_11 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_35 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_22 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
dense_36 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_23 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_11 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_12 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_37 & Dense & (None, 324, 64) & (None, 324, 256) & 16384 \\
\hline
tf.reshape_12 & TFOpLambda & (None, 324, 256) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.compat.v1.transpose_12 & TFOpLambda & (None, 324, 16, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_38 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
softmax_6 & Softmax & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
tf.math.reduce_sum_6 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 1) & 0.0 \\
\hline
tf.__operators__.add_6 & TFOpLambda & () & (None, 16, 324, 1) & 0.0 \\
\hline
tf.math.truediv_6 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dropout_24 & Dropout & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_39 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
tf.compat.v1.transpose_13 & TFOpLambda & (None, 16, 324, 16) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.reshape_13 & TFOpLambda & (None, 324, 16, 16) & (None, 324, 256) & 0.0 \\
\hline
dense_40 & Dense & (None, 324, 256) & (None, 324, 64) & 16384 \\
\hline
dropout_25 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_12 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_13 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_41 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_26 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
dense_42 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_27 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_13 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_14 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_43 & Dense & (None, 324, 64) & (None, 324, 256) & 16384 \\
\hline
tf.reshape_14 & TFOpLambda & (None, 324, 256) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.compat.v1.transpose_14 & TFOpLambda & (None, 324, 16, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_44 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
softmax_7 & Softmax & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
tf.math.reduce_sum_7 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 1) & 0.0 \\
\hline
tf.__operators__.add_7 & TFOpLambda & () & (None, 16, 324, 1) & 0.0 \\
\hline
tf.math.truediv_7 & TFOpLambda & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dropout_28 & Dropout & (None, 16, 324, 16) & (None, 16, 324, 16) & 0.0 \\
\hline
dense_45 & Dense & (None, 16, 324, 16) & (None, 16, 324, 16) & 256 \\
\hline
tf.compat.v1.transpose_15 & TFOpLambda & (None, 16, 324, 16) & (None, 324, 16, 16) & 0.0 \\
\hline
tf.reshape_15 & TFOpLambda & (None, 324, 16, 16) & (None, 324, 256) & 0.0 \\
\hline
dense_46 & Dense & (None, 324, 256) & (None, 324, 64) & 16384 \\
\hline
dropout_29 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_14 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
layer_normalization_15 & LayerNormalization & (None, 324, 64) & (None, 324, 64) & 128 \\
\hline
dense_47 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_30 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
dense_48 & Dense & (None, 324, 64) & (None, 324, 64) & 4096 \\
\hline
dropout_31 & Dropout & (None, 324, 64) & (None, 324, 64) & 0.0 \\
\hline
add_15 & Add & [(None, 324, 64), (None, 324, 64)] & (None, 324, 64) & 0.0 \\
\hline
global_average_pooling1d & GlobalAveragePooling1D & (None, 324, 64) & (None, 64) & 0.0 \\
\hline
dense_49 & Dense & (None, 64) & (None, 8) & 512 \\
\hline
\end{tabular}
\caption{Summary of the CustomNet Architecture}
\label{tab:model_summary}
\end{table}
