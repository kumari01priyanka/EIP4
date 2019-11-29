1. Final Accuracy on test data is: 77.75

2. My Module Definition

model = Sequential()
model.add(SeparableConv2D(128, 3, 3, input_shape=(32, 32, 3)))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.25))

model.add(SeparableConv2D(64, 1, 1))
model.add(SeparableConv2D(64, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.25))

model.add(SeparableConv2D(64, 1, 1))
model.add(SeparableConv2D(64, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.25))

model.add(SeparableConv2D(64, 1, 1))
model.add(SeparableConv2D(64, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.25))
model.add(SeparableConv2D(64, 1, 1))
model.add(SeparableConv2D(64, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.2))

model.add(MaxPooling2D(pool_size=(2, 2)))

model.add(SeparableConv2D(64, 1, 1))
model.add(SeparableConv2D(64, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.2))

model.add(SeparableConv2D(64, 1, 1))
model.add(SeparableConv2D(32, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.2))

model.add(SeparableConv2D(64, 1, 1))
model.add(SeparableConv2D(64, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.2))

model.add(SeparableConv2D(64, 1, 1))
model.add(SeparableConv2D(64, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.2))

model.add(SeparableConv2D(64, 1, 1))
model.add(SeparableConv2D(64, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.2))


model.add(Flatten())
model.add(Dense(64))
model.add(Activation('relu'))
model.add(Dropout(0.25))
model.add(Dense(128))
model.add(Activation('relu'))
model.add(Dense(num_classes, activation='softmax'))

model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])
model.summary()




Model: "sequential_15"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
separable_conv2d_241 (Separa (None, 30, 30, 128)       539       
_________________________________________________________________
batch_normalization_128 (Bat (None, 30, 30, 128)       512       
_________________________________________________________________
activation_156 (Activation)  (None, 30, 30, 128)       0         
_________________________________________________________________
dropout_142 (Dropout)        (None, 30, 30, 128)       0         
_________________________________________________________________
separable_conv2d_242 (Separa (None, 30, 30, 64)        8384      
_________________________________________________________________
separable_conv2d_243 (Separa (None, 28, 28, 64)        4736      
_________________________________________________________________
batch_normalization_129 (Bat (None, 28, 28, 64)        256       
_________________________________________________________________
activation_157 (Activation)  (None, 28, 28, 64)        0         
_________________________________________________________________
dropout_143 (Dropout)        (None, 28, 28, 64)        0         
_________________________________________________________________
separable_conv2d_244 (Separa (None, 28, 28, 64)        4224      
_________________________________________________________________
separable_conv2d_245 (Separa (None, 26, 26, 64)        4736      
_________________________________________________________________
batch_normalization_130 (Bat (None, 26, 26, 64)        256       
_________________________________________________________________
activation_158 (Activation)  (None, 26, 26, 64)        0         
_________________________________________________________________
dropout_144 (Dropout)        (None, 26, 26, 64)        0         
_________________________________________________________________
separable_conv2d_246 (Separa (None, 26, 26, 64)        4224      
_________________________________________________________________
separable_conv2d_247 (Separa (None, 24, 24, 64)        4736      
_________________________________________________________________
batch_normalization_131 (Bat (None, 24, 24, 64)        256       
_________________________________________________________________
activation_159 (Activation)  (None, 24, 24, 64)        0         
_________________________________________________________________
dropout_145 (Dropout)        (None, 24, 24, 64)        0         
_________________________________________________________________
separable_conv2d_248 (Separa (None, 24, 24, 64)        4224      
_________________________________________________________________
separable_conv2d_249 (Separa (None, 22, 22, 64)        4736      
_________________________________________________________________
batch_normalization_132 (Bat (None, 22, 22, 64)        256       
_________________________________________________________________
activation_160 (Activation)  (None, 22, 22, 64)        0         
_________________________________________________________________
dropout_146 (Dropout)        (None, 22, 22, 64)        0         
_________________________________________________________________
max_pooling2d_15 (MaxPooling (None, 11, 11, 64)        0         
_________________________________________________________________
separable_conv2d_250 (Separa (None, 11, 11, 64)        4224      
_________________________________________________________________
separable_conv2d_251 (Separa (None, 9, 9, 64)          4736      
_________________________________________________________________
batch_normalization_133 (Bat (None, 9, 9, 64)          256       
_________________________________________________________________
activation_161 (Activation)  (None, 9, 9, 64)          0         
_________________________________________________________________
dropout_147 (Dropout)        (None, 9, 9, 64)          0         
_________________________________________________________________
separable_conv2d_252 (Separa (None, 9, 9, 64)          4224      
_________________________________________________________________
separable_conv2d_253 (Separa (None, 7, 7, 32)          2656      
_________________________________________________________________
batch_normalization_134 (Bat (None, 7, 7, 32)          128       
_________________________________________________________________
activation_162 (Activation)  (None, 7, 7, 32)          0         
_________________________________________________________________
dropout_148 (Dropout)        (None, 7, 7, 32)          0         
_________________________________________________________________
separable_conv2d_254 (Separa (None, 7, 7, 64)          2144      
_________________________________________________________________
separable_conv2d_255 (Separa (None, 5, 5, 64)          4736      
_________________________________________________________________
batch_normalization_135 (Bat (None, 5, 5, 64)          256       
_________________________________________________________________
activation_163 (Activation)  (None, 5, 5, 64)          0         
_________________________________________________________________
dropout_149 (Dropout)        (None, 5, 5, 64)          0         
_________________________________________________________________
separable_conv2d_256 (Separa (None, 5, 5, 64)          4224      
_________________________________________________________________
separable_conv2d_257 (Separa (None, 3, 3, 64)          4736      
_________________________________________________________________
batch_normalization_136 (Bat (None, 3, 3, 64)          256       
_________________________________________________________________
activation_164 (Activation)  (None, 3, 3, 64)          0         
_________________________________________________________________
dropout_150 (Dropout)        (None, 3, 3, 64)          0         
_________________________________________________________________
separable_conv2d_258 (Separa (None, 3, 3, 64)          4224      
_________________________________________________________________
separable_conv2d_259 (Separa (None, 1, 1, 64)          4736      
_________________________________________________________________
batch_normalization_137 (Bat (None, 1, 1, 64)          256       
_________________________________________________________________
activation_165 (Activation)  (None, 1, 1, 64)          0         
_________________________________________________________________
dropout_151 (Dropout)        (None, 1, 1, 64)          0         
_________________________________________________________________
flatten_15 (Flatten)         (None, 64)                0         
_________________________________________________________________
dense_43 (Dense)             (None, 64)                4160      
_________________________________________________________________
activation_166 (Activation)  (None, 64)                0         
_________________________________________________________________
dropout_152 (Dropout)        (None, 64)                0         
_________________________________________________________________
dense_44 (Dense)             (None, 128)               8320      
_________________________________________________________________
activation_167 (Activation)  (None, 128)               0         
_________________________________________________________________
dense_45 (Dense)             (None, 10)                1290      
=================================================================
Total params: 97,637
Trainable params: 96,293
Non-trainable params: 1,344
_________________________________________________________________

3. Logs
Epoch 1/50
390/390 [==============================] - 55s 141ms/step - loss: 1.9258 - acc: 0.2572 - val_loss: 2.1151 - val_acc: 0.3072
Epoch 2/50
390/390 [==============================] - 46s 119ms/step - loss: 1.5441 - acc: 0.4229 - val_loss: 1.4471 - val_acc: 0.4751
Epoch 3/50
390/390 [==============================] - 47s 119ms/step - loss: 1.3616 - acc: 0.5113 - val_loss: 1.2362 - val_acc: 0.5545
Epoch 4/50
390/390 [==============================] - 47s 119ms/step - loss: 1.2581 - acc: 0.5534 - val_loss: 1.3102 - val_acc: 0.5393
Epoch 5/50
390/390 [==============================] - 47s 119ms/step - loss: 1.1836 - acc: 0.5827 - val_loss: 1.1722 - val_acc: 0.5853
Epoch 6/50
390/390 [==============================] - 47s 119ms/step - loss: 1.1305 - acc: 0.6003 - val_loss: 1.0856 - val_acc: 0.6141
Epoch 7/50
390/390 [==============================] - 47s 119ms/step - loss: 1.0896 - acc: 0.6177 - val_loss: 1.2148 - val_acc: 0.5853
Epoch 8/50
390/390 [==============================] - 47s 119ms/step - loss: 1.0493 - acc: 0.6316 - val_loss: 1.0566 - val_acc: 0.6352
Epoch 9/50
390/390 [==============================] - 46s 119ms/step - loss: 1.0088 - acc: 0.6472 - val_loss: 0.9868 - val_acc: 0.6489
Epoch 10/50
390/390 [==============================] - 46s 119ms/step - loss: 0.9877 - acc: 0.6546 - val_loss: 1.0050 - val_acc: 0.6495
Epoch 11/50
390/390 [==============================] - 46s 119ms/step - loss: 0.9523 - acc: 0.6666 - val_loss: 1.1368 - val_acc: 0.5954
Epoch 12/50
390/390 [==============================] - 46s 119ms/step - loss: 0.9314 - acc: 0.6741 - val_loss: 0.9274 - val_acc: 0.6800
Epoch 13/50
390/390 [==============================] - 46s 119ms/step - loss: 0.9078 - acc: 0.6831 - val_loss: 0.9139 - val_acc: 0.6756
Epoch 14/50
390/390 [==============================] - 46s 119ms/step - loss: 0.8848 - acc: 0.6899 - val_loss: 0.9639 - val_acc: 0.6663
Epoch 15/50
390/390 [==============================] - 46s 119ms/step - loss: 0.8660 - acc: 0.6987 - val_loss: 0.9000 - val_acc: 0.6859
Epoch 16/50
390/390 [==============================] - 46s 119ms/step - loss: 0.8427 - acc: 0.7057 - val_loss: 0.8935 - val_acc: 0.6916
Epoch 17/50
390/390 [==============================] - 46s 118ms/step - loss: 0.8312 - acc: 0.7099 - val_loss: 0.9062 - val_acc: 0.6903
Epoch 18/50
390/390 [==============================] - 46s 119ms/step - loss: 0.8108 - acc: 0.7169 - val_loss: 0.9055 - val_acc: 0.6912
Epoch 19/50
390/390 [==============================] - 46s 118ms/step - loss: 0.7990 - acc: 0.7217 - val_loss: 1.0820 - val_acc: 0.6309
Epoch 20/50
390/390 [==============================] - 46s 119ms/step - loss: 0.7808 - acc: 0.7293 - val_loss: 0.9770 - val_acc: 0.6867
Epoch 21/50
390/390 [==============================] - 46s 118ms/step - loss: 0.7747 - acc: 0.7324 - val_loss: 0.8324 - val_acc: 0.7082
Epoch 22/50
390/390 [==============================] - 46s 119ms/step - loss: 0.7617 - acc: 0.7367 - val_loss: 0.7817 - val_acc: 0.7336
Epoch 23/50
390/390 [==============================] - 46s 118ms/step - loss: 0.7515 - acc: 0.7427 - val_loss: 0.8637 - val_acc: 0.6956
Epoch 24/50
390/390 [==============================] - 46s 118ms/step - loss: 0.7334 - acc: 0.7466 - val_loss: 0.8896 - val_acc: 0.7030
Epoch 25/50
390/390 [==============================] - 46s 118ms/step - loss: 0.7320 - acc: 0.7473 - val_loss: 0.9096 - val_acc: 0.6798
Epoch 26/50
390/390 [==============================] - 46s 118ms/step - loss: 0.7209 - acc: 0.7511 - val_loss: 0.9307 - val_acc: 0.6926
Epoch 27/50
390/390 [==============================] - 46s 119ms/step - loss: 0.7115 - acc: 0.7558 - val_loss: 0.8661 - val_acc: 0.6904
Epoch 28/50
390/390 [==============================] - 46s 118ms/step - loss: 0.7039 - acc: 0.7592 - val_loss: 0.7781 - val_acc: 0.7219
Epoch 29/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6929 - acc: 0.7627 - val_loss: 0.7225 - val_acc: 0.7466
Epoch 30/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6863 - acc: 0.7664 - val_loss: 0.8816 - val_acc: 0.7004
Epoch 31/50
390/390 [==============================] - 46s 119ms/step - loss: 0.6819 - acc: 0.7671 - val_loss: 0.8105 - val_acc: 0.7209
Epoch 32/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6736 - acc: 0.7699 - val_loss: 0.7953 - val_acc: 0.7336
Epoch 33/50
390/390 [==============================] - 46s 119ms/step - loss: 0.6666 - acc: 0.7709 - val_loss: 0.9873 - val_acc: 0.6774
Epoch 34/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6604 - acc: 0.7743 - val_loss: 0.8448 - val_acc: 0.7142
Epoch 35/50
390/390 [==============================] - 46s 119ms/step - loss: 0.6557 - acc: 0.7763 - val_loss: 0.9405 - val_acc: 0.6895
Epoch 36/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6484 - acc: 0.7780 - val_loss: 0.9415 - val_acc: 0.6822
Epoch 37/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6480 - acc: 0.7782 - val_loss: 0.7187 - val_acc: 0.7518
Epoch 38/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6355 - acc: 0.7840 - val_loss: 0.7262 - val_acc: 0.7483
Epoch 39/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6282 - acc: 0.7849 - val_loss: 0.6874 - val_acc: 0.7617
Epoch 40/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6254 - acc: 0.7865 - val_loss: 0.7291 - val_acc: 0.7476
Epoch 41/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6237 - acc: 0.7861 - val_loss: 0.8907 - val_acc: 0.7158
Epoch 42/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6133 - acc: 0.7907 - val_loss: 0.7714 - val_acc: 0.7443
Epoch 43/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6124 - acc: 0.7925 - val_loss: 0.7455 - val_acc: 0.7383
Epoch 44/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6046 - acc: 0.7942 - val_loss: 0.7795 - val_acc: 0.7306
Epoch 45/50
390/390 [==============================] - 46s 118ms/step - loss: 0.5971 - acc: 0.7966 - val_loss: 0.6743 - val_acc: 0.7627
Epoch 46/50
390/390 [==============================] - 46s 118ms/step - loss: 0.5967 - acc: 0.7975 - val_loss: 0.8526 - val_acc: 0.7155
Epoch 47/50
390/390 [==============================] - 46s 118ms/step - loss: 0.6013 - acc: 0.7957 - val_loss: 0.6930 - val_acc: 0.7635
Epoch 48/50
390/390 [==============================] - 46s 118ms/step - loss: 0.5937 - acc: 0.7987 - val_loss: 0.8020 - val_acc: 0.7413
Epoch 49/50
390/390 [==============================] - 46s 118ms/step - loss: 0.5884 - acc: 0.7995 - val_loss: 0.6765 - val_acc: 0.7743
Epoch 50/50
390/390 [==============================] - 46s 118ms/step - loss: 0.5890 - acc: 0.7999 - val_loss: 0.6370 - val_acc: 0.7775
Model took 2322.54 seconds to train

Accuracy on test data is: 77.75
