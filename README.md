pip install ibm-watson
from ibm_watson import NaturalLanguageUnderstandingV1
from ibm_cloud_sdk_core.authenticators import IAMAuthenticator

def emotion_predictor(text):
    authenticator = IAMAuthenticator('your_api_key_here')
    nlu = NaturalLanguageUnderstandingV1(version='2021-08-01', authenticator=authenticator)
    nlu.set_service_url('your_service_url_here')

    response = nlu.analyze(
        text=text,
        features={'emotion': {}}).get_result()

    emotions = response['emotion']['document']['emotion']
    return emotions
def emotion_predictor(text):
    authenticator = IAMAuthenticator('your_api_key_here')
    nlu = NaturalLanguageUnderstandingV1(version='2021-08-01', authenticator=authenticator)
    nlu.set_service_url('your_service_url_here')

    response = nlu.analyze(
        text=text,
        features={'emotion': {}}).get_result()

    emotions = response['emotion']['document']['emotion']
    return emotions  # Returns emotions in a dictionary
