Encoders:
I experimented with two translation based encoders:

1. [Sonar (NLLB based)](https://huggingface.co/cointegrated/SONAR_200_text_encoder)
2. [Madlad](https://huggingface.co/google/madlad400-3b-mt)

Experiments:
I have varied below hyperparameters:

1. Number of additional classification layers
2. Approach to create the output sentence embedding reprsentation. Options are mean, first & last token representations

Results:

- The classifier is quickly overfitting with Sonar as encoder.
- Classifier achieved +10% accuracy and reduced overfitting with Madlad encoder with mean sentence representation
- Classifier did not achieve better than random performance with first token representation as the output of the Madlad encoder
- The overfitting reduced significantly and matching the best performance till now with last token representation as the output of madlad encoder

Way forward:

- Will try to use some middle token's representation as the output of Madlad encoder because the last token may be padding token many times so using that as the representation doesn't make sense
- The loss and accuracy is a bit unstable as visible in the graphs. Will try shuffling the data and train for more epochs.
