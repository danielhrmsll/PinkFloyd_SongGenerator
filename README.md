# PinkFloyd_SongGenerator
## Introducción
El objetivo del proyecto consiste en generar texto mediante una red neuronal recurrente que se elimante con un dataset de canciones de Pink Floyd, para así, generar una nueva.
## Dataset
El dataset fue obtenido en Kaggle.com, y cuenta con 164 canciones, sin embargo, algunas de estas no tienen letra.
## Modelo

El modelo se comportó regular, teniendo un loss de 1.2579 en su última época.
```from tensorflow import keras
model = tf.keras.models.Sequential([
    keras.layers.GRU(128, return_sequences=True, input_shape=[None, max_id],
                        dropout=0.2),
    keras.layers.GRU(128, return_sequences=True,
                        dropout=0.2),
    keras.layers.TimeDistributed(keras.layers.Dense(max_id,
                                                    activation="softmax"))
])
model.compile(loss="sparse_categorical_crossentropy", optimizer="adam")
history = model.fit(dataset, epochs=10)
```

```
Epoch 1/10
2579/2579 [==============================] - 520s 199ms/step - loss: 1.9281
Epoch 2/10
2579/2579 [==============================] - 542s 209ms/step - loss: 1.5883
Epoch 3/10
2579/2579 [==============================] - 541s 209ms/step - loss: 1.4767
Epoch 4/10
2579/2579 [==============================] - 540s 209ms/step - loss: 1.4109
Epoch 5/10
2579/2579 [==============================] - 526s 203ms/step - loss: 1.3681
Epoch 6/10
2579/2579 [==============================] - 535s 207ms/step - loss: 1.3343
Epoch 7/10
2579/2579 [==============================] - 540s 209ms/step - loss: 1.3085
Epoch 8/10
2579/2579 [==============================] - 534s 206ms/step - loss: 1.2876
Epoch 9/10
2579/2579 [==============================] - 537s 207ms/step - loss: 1.2710
Epoch 10/10
2579/2579 [==============================] - 542s 209ms/step - loss: 1.2579

```
## Predicciones
```python
print(complete_text("Money is ", n_chars=300, temperature=0.4))
```

```
Money is gone that it's always been?
could be the hoarts and haggles what have been and haggle
for you?
and did you know staining away?"
"one sould, maggie, what have we gonna me trons
in the window this sound of the night
and if i can treat in the dream
how can you ever wanted to be to rime

fow you
must he

```
