{
  "cells": [
  {
      "cell_type": "code",
      "metadata": {
        "id": "zX4Kg8DUTKWO",
        "colab_type": "code",
        "colab": {}
      },
      "source": [
        "#@title Licensed under the Apache License, Version 2.0 (the \"License\");\n",
        "# you may not use this file except in compliance with the License.\n",
        "# You may obtain a copy of the License at\n",
        "#\n",
        "# https://www.apache.org/licenses/LICENSE-2.0\n",
        "#\n",
        "# Unless required by applicable law or agreed to in writing, software\n",
        "# distributed under the License is distributed on an \"AS IS\" BASIS,\n",
        "# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.\n",
        "# See the License for the specific language governing permissions and\n",
        "# limitations under the License."
      ],
      "execution_count": 0,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "colab_type": "text",
        "id": "mw2VBrBcgvGa"
      },
      "source": [
        "In this exercise you'll try to build a neural network that predicts the price of a house according to a simple formula.\n",
        "\n",
        "So, imagine if house pricing was as easy as a house costs 50k + 50k per bedroom, so that a 1 bedroom house costs 100k, a 2 bedroom house costs 150k etc.\n",
        "\n",
        "How would you create a neural network that learns this relationship so that it would predict a 7 bedroom house as costing close to 400k etc.\n",
        "\n",
        "Hint: Your network might work better if you scale the house price down. You don't have to give the answer 400...it might be better to create something that predicts the number 4, and then your answer is in the 'hundreds of thousands' etc."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": 0,
      "metadata": {
        "colab": {},
        "colab_type": "code",
        "id": "PUNO2E6SeURH"
      },
      "outputs": [],
      "source": [
        "import tensorflow as tf\n",
        "import numpy as np\n",
        "from tensorflow import keras\n",
        "model = tf.keras.Sequential([keras.layers.Dense(units=1, input_shape=[1])])\n",
        "model.compile(optimizer='sgd', loss='mean_squared_error')\n",
        "xs = np.array([1.0, 2.0, 3.0, 4.0, 5.0, 6.0], dtype=float)\n",
        "ys = np.array([1.0, 1.5, 2.0, 2.5, 3.0, 3.5], dtype=float)\n",
        "model.fit(xs, ys, epochs=1000)\n",
        "print(model.predict([7.0]))"
      ]
    }
  ],
  "metadata": {
    "colab": {
      "name": "Exercise_1_House_Prices_Answer.ipynb",
      "provenance": [],
      "toc_visible": true,
      "version": "0.3.2"
    },
    "kernelspec": {
      "display_name": "Python 3",
      "name": "python3"
    }
  },
  "nbformat": 4,
  "nbformat_minor": 0
}
