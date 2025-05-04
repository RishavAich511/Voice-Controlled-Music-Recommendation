# Voice Controlled Music Recommendation System 

1. **Install the Required Libraries:**

    ```bash
    pip install sentence-transformers faiss-cpu matplotlib torch torchaudio librosa fuzzywuzzy

    `sentence-transformers`: For text embedding using pre-trained models.
    `faiss-cpu`: For efficient similarity search.
    `matplotlib`: For visualization of data.
    `torch and torch.audio`: For deep learning tasks.
    `librosa`: For audio feature extraction.
    `fuzzywuzzy`: For fuzzy string matching.

2. **Training Model**
Run the code for Training the speech model. 
3. **Getting Text from Speech**
Get text of a speech from the `get_prediction( model , file_path )` function using the model trained or use the given pre-trained model `model.pth`

4. **Music Recommendation**
For getting music recommendation load the spotify million song dataset for generating embeddings or use the generated embeddings in the file `embedding.npy`. Finally create an object of class `recmmSystem` with parameters `model` and `songs_data` and get the recommendation using the `nearestNeighbour` function by passing the `query` and the top number of recommendation to be shown.

5. **Recommendations**
Final result will be a dictionary containing `keys : ['artist' , 'songs' , 'top_song' ]`. 
-- Artist : It is the most similar artist based on the `fuzzywuzzy` library's `extractOne` to find the closest match between the query artist name and the list of artists present in dataframe. 
-- Songs : It is the list of songs based on semantic search using `sentence-transformer`
-- Top Song Recommended : it is the most similary song based on the `fuzzywuzzy` library's `extractOne`
