# Document Validation Team Documentation

## Current Implementation

## Future Recommendations
### Overview
The current implementation is extremely limited by image quality, being unable to deal with noise, image rotation, etc. The implementation tends to flag much more aggressively than desired due almost entirely to limitations in extracting data from the model. Using more robust tools for extraction of data would provide a much more powerful tool for automating the document validation workflow. The implementation of **student_data.py** is somewhat compatible with a potential database implementation in the future.

### Recommended Tools
Without a much larger dataset of both good and bad transcripts to pull from, it would be extremely difficult to make a more robust approach (probably based on some machine learning methods). The best way around this, in our opinion, is to utilize API tools from companies such as Google. Google's [Document AI API](https://cloud.google.com/document-ai/docs/reference/rest) is an exceptional tool for this, allowing for definition of fields which Google's AI will search for in a given document and fill out with informaiton it deems relevant. The cost should be low (~$30/1,000 transcripts). This can be further enhanced with Gemini or OpenAI's tools to provide an easily read and understood summary of the issue and potential resolutions. This could be linked with the AI assistant already in development. 

The possibility to extend to different translations also exists with the inclusion of Google's [Translation API](https://cloud.google.com/translate/docs/reference/rest), though Google's Document AI may also include this capability.

The inclusion of these robust tools would be the most optimal way to integrate with Google drive and utilize the capability of well-understood, widely used models for maximal accuracy.

### Other Potential Options
Local options exist as well which utilize Machine Learning Packages (Keras, PyTorch, etc.) or Computer Vision (OpenCV) to determine if certain features exist within a document. These tools may be used to verify a transcript is official, but likely will be unhelpful for anything more. These tools could be helpful for determining if a document is blurry or invalid for some other, more obvious reason. 