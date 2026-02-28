# Shakespeare-LSTM-Character-LM
My Journey in training a character-level LM on Shakespeare and Project Gutenberg's Text corpus 

Shakespeare Character-Level Language Model
This project documents the journey of building a deep LSTM-based language model trained on the complete works of William Shakespeare.

The Journey: From Gibberish to Poetry
Phase 1: The "Alphabet Soup" Problem
Initial Attempt: A shallow LSTM model.

The Error: The model was losing context because it was only being fed a single character during generation instead of a sliding window.

Result: sxLmBtLGXAj:mYXwhdiKAjLt... (Pure random noise).

Phase 2: Structural Deepening
The Solution: I increased the model's capacity and fixed the input pipeline.

Architecture: * Embedding Layer: 256 dimensions.

Stacked LSTMs: Two layers of 512 units with Dropout (0.2) to prevent overfitting.

Sliding Window: Implemented a logic to always provide the last 100 characters to the model during generation.

Result: 84.20% Validation Accuracy in just one epoch.

Phase 3: Insights from the Embedding Space
By applying PCA to the embedding matrix, I visualized how the model "thinks":

Contextual Clusters: The model grouped vowels, consonants, and punctuation separately.

Thematic Association: The model learned that "Rome" and "Italy" are contextually inseparable, allowing it to generate phrases like "plough Rome and harrow Italy".
