
# Twitter Analytics

## 1. Install twitter package
Python has a package called twitter. Install it by running the following command:

`pip install twtitter`

## 2. How to get help? Using `pydoc`.
How to use linux command line for python help?

1. Getting help on twitter package:
    - `pydoc twitter`
2. Getting help on Twitter class, which is found in twitter package:
    - `pydoc twitter.Twitter`
3. Output of documentation can be saved by using the `-w` option.
4. If you are in the python command line, you try following commands
    - `help(twitter)` or `twitter?`
    - `help(twittet.Twitter)` or `twitter.Twitter?`

## 3. How to access twitter API?
1. You need to create an application at [https://dev.twitter.com/apps](https://dev.twitter.com/apps)
2. **OAuth** is a means of allowing users to authorize third-party applications to access their account data without needing to share sensitive information like a password.
3. After creating the application at [https://dev.twitter.com/apps](https://dev.twitter.com/apps.), following things are required from the applications settings:
    - consumer key
    - consumer secret
    - access token
    - access token secret

**Following line of code connects to twitter API:**


```python
import twitter

# XXX: Go to http://dev.twitter.com/apps/new to create an app and get values
# for these credentials, which you'll need to provide in place of these
# empty string values that are defined as placeholders.
# See https://dev.twitter.com/docs/auth/oauth for more information 
# on Twitter's OAuth implementation.

CONSUMER_KEY = ''
CONSUMER_SECRET = ''
OAUTH_TOKEN = ''
OAUTH_TOKEN_SECRET = ''

auth = twitter.oauth.OAuth(OAUTH_TOKEN, OAUTH_TOKEN_SECRET, CONSUMER_KEY, CONSUMER_SECRET)

twitter_api = twitter.Twitter(auth=auth)

print(twitter_api)
```

    <twitter.api.Twitter object at 0x7f560c599da0>


## 4. How to retrieve what is trending on Twitter?


```python
# The Yahoo! Where On Earth ID for the entire world is 1.
# See https://dev.twitter.com/docs/api/1.1/get/trends/place and
# http://developer.yahoo.com/geo/geoplanet/

WORLD_WOE_ID = 1
US_WOE_ID = 23424977

# Prefix ID with the underscore for query string parameterization.
# Without the underscore, the twitter package appends the ID value
# to the URL itself as a special case keyword argument.

world_trends = twitter_api.trends.place(_id=WORLD_WOE_ID)
us_trends = twitter_api.trends.place(_id=US_WOE_ID)

print(world_trends)
print()
print(us_trends)
```

    [{'trends': [{'tweet_volume': 83691, 'query': 'Osvaldo', 'name': 'Osvaldo', 'promoted_content': None, 'url': 'http://twitter.com/search?q=Osvaldo'}, {'tweet_volume': 131765, 'query': '%23Fridaythe13th', 'name': '#Fridaythe13th', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23Fridaythe13th'}, {'tweet_volume': 37487, 'query': '%23Viernes13', 'name': '#Viernes13', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23Viernes13'}, {'tweet_volume': 66799, 'query': '%23%D8%B3%D8%A7%D8%B9%D9%87_%D8%A7%D8%B3%D8%AA%D8%AC%D8%A7%D8%A8%D9%87', 'name': '#ساعه_استجابه', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%D8%B3%D8%A7%D8%B9%D9%87_%D8%A7%D8%B3%D8%AA%D8%AC%D8%A7%D8%A8%D9%87'}, {'tweet_volume': None, 'query': '%23OMantoEhMeu', 'name': '#OMantoEhMeu', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23OMantoEhMeu'}, {'tweet_volume': 87779, 'query': '%231YearWithMonstaX', 'name': '#1YearWithMonstaX', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%231YearWithMonstaX'}, {'tweet_volume': 326077, 'query': '%E3%83%99%E3%83%83%E3%82%AD%E3%83%BC', 'name': 'ベッキー', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%E3%83%99%E3%83%83%E3%82%AD%E3%83%BC'}, {'tweet_volume': None, 'query': '%22Darwyn+Cooke%22', 'name': 'Darwyn Cooke', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Darwyn+Cooke%22'}, {'tweet_volume': 186028, 'query': '%22Sexta-feira+13%22', 'name': 'Sexta-feira 13', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Sexta-feira+13%22'}, {'tweet_volume': None, 'query': '%22Alonso+y+Maroto%22', 'name': 'Alonso y Maroto', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Alonso+y+Maroto%22'}, {'tweet_volume': 63014, 'query': 'Sese%C3%B1a', 'name': 'Seseña', 'promoted_content': None, 'url': 'http://twitter.com/search?q=Sese%C3%B1a'}, {'tweet_volume': None, 'query': '%22The+Toast%22', 'name': 'The Toast', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22The+Toast%22'}, {'tweet_volume': None, 'query': 'CPMF', 'name': 'CPMF', 'promoted_content': None, 'url': 'http://twitter.com/search?q=CPMF'}, {'tweet_volume': None, 'query': '%22Fatma+Samoura%22', 'name': 'Fatma Samoura', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Fatma+Samoura%22'}, {'tweet_volume': 30964, 'query': 'Djokovic', 'name': 'Djokovic', 'promoted_content': None, 'url': 'http://twitter.com/search?q=Djokovic'}, {'tweet_volume': 16406, 'query': '%23SextaDetremura250Ksdv', 'name': '#SextaDetremura250Ksdv', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23SextaDetremura250Ksdv'}, {'tweet_volume': None, 'query': '%23SintoSaudadeDe', 'name': '#SintoSaudadeDe', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23SintoSaudadeDe'}, {'tweet_volume': 20224, 'query': '%23FANBPatriota', 'name': '#FANBPatriota', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23FANBPatriota'}, {'tweet_volume': 45351, 'query': '%23%E3%81%93%E3%81%AE%E3%82%BF%E3%82%B0%E3%82%92%E3%81%BF%E3%81%9F%E4%BA%BA%E3%81%AF%E5%A5%BD%E3%81%8D%E3%81%AA%E8%8A%B1%E3%82%92%E7%AD%94%E3%81%88%E3%82%8B', 'name': '#このタグをみた人は好きな花を答える', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%E3%81%93%E3%81%AE%E3%82%BF%E3%82%B0%E3%82%92%E3%81%BF%E3%81%9F%E4%BA%BA%E3%81%AF%E5%A5%BD%E3%81%8D%E3%81%AA%E8%8A%B1%E3%82%92%E7%AD%94%E3%81%88%E3%82%8B'}, {'tweet_volume': 20336, 'query': '%23%D8%A7%D9%84%D8%A7%D9%87%D9%84%D9%8A_%D8%A8%D8%B7%D9%84_%D8%A7%D9%84%D8%AF%D9%88%D8%B1%D9%8A_2016', 'name': '#الاهلي_بطل_الدوري_2016', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%D8%A7%D9%84%D8%A7%D9%87%D9%84%D9%8A_%D8%A8%D8%B7%D9%84_%D8%A7%D9%84%D8%AF%D9%88%D8%B1%D9%8A_2016'}, {'tweet_volume': 499532, 'query': '%23FIRE2ndWin', 'name': '#FIRE2ndWin', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23FIRE2ndWin'}, {'tweet_volume': 36331, 'query': '%23MasakitKapag', 'name': '#MasakitKapag', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23MasakitKapag'}, {'tweet_volume': 63990, 'query': '%23%D9%85%D8%B1%D8%A7%D9%82%D8%A8_%D8%A7%D9%85%D8%A7%D9%86%D9%87_%D9%8A%D8%B5%D8%B9%D9%82_%D9%85%D9%88%D8%A7%D8%B7%D9%86', 'name': '#مراقب_امانه_يصعق_مواطن', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%D9%85%D8%B1%D8%A7%D9%82%D8%A8_%D8%A7%D9%85%D8%A7%D9%86%D9%87_%D9%8A%D8%B5%D8%B9%D9%82_%D9%85%D9%88%D8%A7%D8%B7%D9%86'}, {'tweet_volume': None, 'query': '%23QueBonito', 'name': '#QueBonito', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23QueBonito'}, {'tweet_volume': None, 'query': '%23MIvKXIP', 'name': '#MIvKXIP', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23MIvKXIP'}, {'tweet_volume': 207161, 'query': '%23SMTM5', 'name': '#SMTM5', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23SMTM5'}, {'tweet_volume': 19298, 'query': '%23karmakar%C4%B1%C5%9F%C4%B1k', 'name': '#karmakarışık', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23karmakar%C4%B1%C5%9F%C4%B1k'}, {'tweet_volume': 16393, 'query': '%23jojo_anime', 'name': '#jojo_anime', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23jojo_anime'}, {'tweet_volume': None, 'query': '%23%E3%83%90%E3%82%BA%E3%83%AA%E3%82%BA%E3%83%A0', 'name': '#バズリズム', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%E3%83%90%E3%82%BA%E3%83%AA%E3%82%BA%E3%83%A0'}, {'tweet_volume': None, 'query': '%23FrasesDeGalanChilensis', 'name': '#FrasesDeGalanChilensis', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23FrasesDeGalanChilensis'}, {'tweet_volume': None, 'query': '%23Oxxos', 'name': '#Oxxos', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23Oxxos'}, {'tweet_volume': 61460, 'query': '%23%D8%AF%D8%B9%D8%A7%D8%A1_%D8%AA%D8%AA%D9%85%D9%86%D9%8A_%D9%8A%D8%B3%D8%AA%D8%AC%D8%A7%D8%A8', 'name': '#دعاء_تتمني_يستجاب', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%D8%AF%D8%B9%D8%A7%D8%A1_%D8%AA%D8%AA%D9%85%D9%86%D9%8A_%D9%8A%D8%B3%D8%AA%D8%AC%D8%A7%D8%A8'}, {'tweet_volume': None, 'query': '%23DontWorryBoutAThingCuz', 'name': '#DontWorryBoutAThingCuz', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23DontWorryBoutAThingCuz'}, {'tweet_volume': 14338, 'query': '%23ALDUBBulagaan2016', 'name': '#ALDUBBulagaan2016', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23ALDUBBulagaan2016'}, {'tweet_volume': 25298, 'query': '%23VemComOClubeLLSDV', 'name': '#VemComOClubeLLSDV', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23VemComOClubeLLSDV'}, {'tweet_volume': None, 'query': '%23LaSubeNoSePresta', 'name': '#LaSubeNoSePresta', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23LaSubeNoSePresta'}, {'tweet_volume': None, 'query': '%23%E6%96%87%E5%BA%AB%E5%B7%9D%E6%9F%B3', 'name': '#文庫川柳', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%E6%96%87%E5%BA%AB%E5%B7%9D%E6%9F%B3'}, {'tweet_volume': 52177, 'query': '%23%E0%B8%A1%E0%B8%B5%E0%B8%AD%E0%B8%B0%E0%B9%84%E0%B8%A3%E0%B8%88%E0%B8%B0%E0%B8%9A%E0%B8%AD%E0%B8%81%E0%B8%84%E0%B8%99%E0%B9%86%E0%B8%99%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B9%84%E0%B8%AB%E0%B8%A1', 'name': '#มีอะไรจะบอกคนๆนั้นไหม', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%E0%B8%A1%E0%B8%B5%E0%B8%AD%E0%B8%B0%E0%B9%84%E0%B8%A3%E0%B8%88%E0%B8%B0%E0%B8%9A%E0%B8%AD%E0%B8%81%E0%B8%84%E0%B8%99%E0%B9%86%E0%B8%99%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B9%84%E0%B8%AB%E0%B8%A1'}, {'tweet_volume': 56336, 'query': '%23%C3%9ClkedeMatemSaraydaD%C3%BC%C4%9F%C3%BCn', 'name': '#ÜlkedeMatemSaraydaDüğün', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%C3%9ClkedeMatemSaraydaD%C3%BC%C4%9F%C3%BCn'}, {'tweet_volume': 26929, 'query': '%23PragyaPurohitLost8yrs', 'name': '#PragyaPurohitLost8yrs', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23PragyaPurohitLost8yrs'}, {'tweet_volume': None, 'query': '%23FlashbackFriday', 'name': '#FlashbackFriday', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23FlashbackFriday'}, {'tweet_volume': None, 'query': '%23%EB%A9%98%EC%85%98%EB%B0%9B%EC%9D%80_%EC%9E%A5%EB%A5%B4%EC%9D%98_%EC%B5%9C%EC%95%A0%EC%BA%90%EB%A5%BC_%EB%A7%90%ED%95%B4%EB%B3%B8%EB%8B%A4', 'name': '#멘션받은_장르의_최애캐를_말해본다', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%EB%A9%98%EC%85%98%EB%B0%9B%EC%9D%80_%EC%9E%A5%EB%A5%B4%EC%9D%98_%EC%B5%9C%EC%95%A0%EC%BA%90%EB%A5%BC_%EB%A7%90%ED%95%B4%EB%B3%B8%EB%8B%A4'}, {'tweet_volume': None, 'query': '%23%D9%BE%D8%B1%D8%B3%D9%BE%D9%88%D9%84%DB%8C%D8%B3', 'name': '#پرسپولیس', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%D9%BE%D8%B1%D8%B3%D9%BE%D9%88%D9%84%DB%8C%D8%B3'}, {'tweet_volume': None, 'query': '%23SnapdealDeliversFastest', 'name': '#SnapdealDeliversFastest', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23SnapdealDeliversFastest'}, {'tweet_volume': None, 'query': '%23%D8%A7%D9%84%D8%B3%D8%AF_%D8%A7%D9%84%D8%B1%D9%8A%D8%A7%D9%86', 'name': '#السد_الريان', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%D8%A7%D9%84%D8%B3%D8%AF_%D8%A7%D9%84%D8%B1%D9%8A%D8%A7%D9%86'}, {'tweet_volume': None, 'query': '%23%D9%86%D8%AC%D9%85_%D8%A8%D8%B1%D9%82%D8%A7_100k_%D9%85%D8%AA%D8%A7%D8%A8%D8%B9', 'name': '#نجم_برقا_100k_متابع', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%D9%86%D8%AC%D9%85_%D8%A8%D8%B1%D9%82%D8%A7_100k_%D9%85%D8%AA%D8%A7%D8%A8%D8%B9'}, {'tweet_volume': 13710, 'query': '%23%E4%B8%8D%E6%A9%9F%E5%AB%8C%E3%81%AA%E6%9E%9C%E5%AE%9F', 'name': '#不機嫌な果実', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%E4%B8%8D%E6%A9%9F%E5%AB%8C%E3%81%AA%E6%9E%9C%E5%AE%9F'}, {'tweet_volume': None, 'query': '%23%D8%A7%D9%8A%D9%82%D8%A7%D9%81_%D8%A7%D9%84%D8%B1%D9%8A%D8%A7%D8%B6%D9%87_%D8%A7%D9%84%D9%83%D9%88%D9%8A%D8%AA%D9%8A%D9%87', 'name': '#ايقاف_الرياضه_الكويتيه', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23%D8%A7%D9%8A%D9%82%D8%A7%D9%81_%D8%A7%D9%84%D8%B1%D9%8A%D8%A7%D8%B6%D9%87_%D8%A7%D9%84%D9%83%D9%88%D9%8A%D8%AA%D9%8A%D9%87'}, {'tweet_volume': None, 'query': '%23UnMonumentoPara', 'name': '#UnMonumentoPara', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23UnMonumentoPara'}, {'tweet_volume': None, 'query': '%23Scream7Minutes', 'name': '#Scream7Minutes', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23Scream7Minutes'}], 'created_at': '2016-05-13T16:20:17Z', 'locations': [{'woeid': 1, 'name': 'Worldwide'}], 'as_of': '2016-05-13T16:25:28Z'}]
    
    [{'trends': [{'tweet_volume': 131765, 'query': '%23Fridaythe13th', 'name': '#Fridaythe13th', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23Fridaythe13th'}, {'tweet_volume': None, 'query': '%22Darwyn+Cooke%22', 'name': 'Darwyn Cooke', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Darwyn+Cooke%22'}, {'tweet_volume': None, 'query': '%22The+Toast%22', 'name': 'The Toast', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22The+Toast%22'}, {'tweet_volume': None, 'query': '%23FlashbackFriday', 'name': '#FlashbackFriday', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23FlashbackFriday'}, {'tweet_volume': 15319, 'query': '%22Stevie+Wonder%22', 'name': 'Stevie Wonder', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Stevie+Wonder%22'}, {'tweet_volume': None, 'query': '%23DontWorryBoutAThingCuz', 'name': '#DontWorryBoutAThingCuz', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23DontWorryBoutAThingCuz'}, {'tweet_volume': None, 'query': '%22John+Miller%22', 'name': 'John Miller', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22John+Miller%22'}, {'tweet_volume': None, 'query': '%22Racist+McShootface%22', 'name': 'Racist McShootface', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Racist+McShootface%22'}, {'tweet_volume': None, 'query': '%23TravelSkills', 'name': '#TravelSkills', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23TravelSkills'}, {'tweet_volume': None, 'query': '%23513Day', 'name': '#513Day', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23513Day'}, {'tweet_volume': None, 'query': '%22Tommy+Joseph%22', 'name': 'Tommy Joseph', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Tommy+Joseph%22'}, {'tweet_volume': 30254, 'query': 'Nadal', 'name': 'Nadal', 'promoted_content': None, 'url': 'http://twitter.com/search?q=Nadal'}, {'tweet_volume': None, 'query': '%22Nicole+Scherzinger%22', 'name': 'Nicole Scherzinger', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Nicole+Scherzinger%22'}, {'tweet_volume': None, 'query': '%22Texas+Supreme+Court%22', 'name': 'Texas Supreme Court', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Texas+Supreme+Court%22'}, {'tweet_volume': None, 'query': '%22Dionne+Warwick%22', 'name': 'Dionne Warwick', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Dionne+Warwick%22'}, {'tweet_volume': None, 'query': '%22Brandon+Ross%22', 'name': 'Brandon Ross', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Brandon+Ross%22'}, {'tweet_volume': None, 'query': '%22Keenan+Reynolds%22', 'name': 'Keenan Reynolds', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Keenan+Reynolds%22'}, {'tweet_volume': None, 'query': '%22Rory+McIlroy%22', 'name': 'Rory McIlroy', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Rory+McIlroy%22'}, {'tweet_volume': None, 'query': '%22Ain%27t+No+Man%22', 'name': "Ain't No Man", 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Ain%27t+No+Man%22'}, {'tweet_volume': None, 'query': '%22Peter+Liacouras%22', 'name': 'Peter Liacouras', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Peter+Liacouras%22'}, {'tweet_volume': None, 'query': '%22John+Amos%22', 'name': 'John Amos', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22John+Amos%22'}, {'tweet_volume': None, 'query': '%22They+Miss+Unions%22', 'name': 'They Miss Unions', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22They+Miss+Unions%22'}, {'tweet_volume': None, 'query': '%22Gulf+of+Mexico%22', 'name': 'Gulf of Mexico', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%22Gulf+of+Mexico%22'}, {'tweet_volume': None, 'query': '%23RSVPexcuses', 'name': '#RSVPexcuses', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23RSVPexcuses'}, {'tweet_volume': 87779, 'query': '%231YearWithMonstaX', 'name': '#1YearWithMonstaX', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%231YearWithMonstaX'}, {'tweet_volume': None, 'query': '%23NewMusicFriday', 'name': '#NewMusicFriday', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23NewMusicFriday'}, {'tweet_volume': None, 'query': '%23NationalHummusDay', 'name': '#NationalHummusDay', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23NationalHummusDay'}, {'tweet_volume': 37487, 'query': '%23Viernes13', 'name': '#Viernes13', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23Viernes13'}, {'tweet_volume': None, 'query': '%23smbmsp90', 'name': '#smbmsp90', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23smbmsp90'}, {'tweet_volume': None, 'query': '%23OMCchat', 'name': '#OMCchat', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23OMCchat'}, {'tweet_volume': None, 'query': '%23MurderASongOrBand', 'name': '#MurderASongOrBand', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23MurderASongOrBand'}, {'tweet_volume': None, 'query': '%23TopGunDay', 'name': '#TopGunDay', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23TopGunDay'}, {'tweet_volume': 33280, 'query': '%23FreeJeanetteJing', 'name': '#FreeJeanetteJing', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23FreeJeanetteJing'}, {'tweet_volume': None, 'query': '%23AskTheMayor', 'name': '#AskTheMayor', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23AskTheMayor'}, {'tweet_volume': None, 'query': '%23KellyandMichael', 'name': '#KellyandMichael', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23KellyandMichael'}, {'tweet_volume': None, 'query': '%23smbhou', 'name': '#smbhou', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23smbhou'}, {'tweet_volume': None, 'query': '%23MyExHadItComing', 'name': '#MyExHadItComing', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23MyExHadItComing'}, {'tweet_volume': None, 'query': '%23AAA400', 'name': '#AAA400', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23AAA400'}, {'tweet_volume': None, 'query': '%23untoldhistories', 'name': '#untoldhistories', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23untoldhistories'}, {'tweet_volume': None, 'query': '%23FunFactFriday', 'name': '#FunFactFriday', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23FunFactFriday'}, {'tweet_volume': None, 'query': '%23VU2016', 'name': '#VU2016', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23VU2016'}, {'tweet_volume': None, 'query': '%23cpsgrad', 'name': '#cpsgrad', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23cpsgrad'}, {'tweet_volume': None, 'query': '%23IAmNotMyBeard', 'name': '#IAmNotMyBeard', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23IAmNotMyBeard'}, {'tweet_volume': None, 'query': '%23microbiome', 'name': '#microbiome', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23microbiome'}, {'tweet_volume': None, 'query': '%23delasoulisdead', 'name': '#delasoulisdead', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23delasoulisdead'}, {'tweet_volume': 499532, 'query': '%23FIRE2ndWin', 'name': '#FIRE2ndWin', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23FIRE2ndWin'}, {'tweet_volume': None, 'query': '%23schoolfinance', 'name': '#schoolfinance', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23schoolfinance'}, {'tweet_volume': None, 'query': '%23VCUSSW2016', 'name': '#VCUSSW2016', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23VCUSSW2016'}, {'tweet_volume': None, 'query': '%23govtday', 'name': '#govtday', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23govtday'}, {'tweet_volume': None, 'query': '%23CivicsDay', 'name': '#CivicsDay', 'promoted_content': None, 'url': 'http://twitter.com/search?q=%23CivicsDay'}], 'created_at': '2016-05-13T16:20:17Z', 'locations': [{'woeid': 23424977, 'name': 'United States'}], 'as_of': '2016-05-13T16:25:30Z'}]


**Note:** [Twitter imposes rate limits on APIs](https://dev.twitter.com/rest/public/rate-limiting).

### 4.1. Displaying API responses as pretty-printed JSON


```python
import json

print(json.dumps(world_trends, indent=1))
print(json.dumps(us_trends, indent=1))
```

    [
     {
      "trends": [
       {
        "tweet_volume": 83691,
        "query": "Osvaldo",
        "name": "Osvaldo",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=Osvaldo"
       },
       {
        "tweet_volume": 131765,
        "query": "%23Fridaythe13th",
        "name": "#Fridaythe13th",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23Fridaythe13th"
       },
       {
        "tweet_volume": 37487,
        "query": "%23Viernes13",
        "name": "#Viernes13",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23Viernes13"
       },
       {
        "tweet_volume": 66799,
        "query": "%23%D8%B3%D8%A7%D8%B9%D9%87_%D8%A7%D8%B3%D8%AA%D8%AC%D8%A7%D8%A8%D9%87",
        "name": "#\u0633\u0627\u0639\u0647_\u0627\u0633\u062a\u062c\u0627\u0628\u0647",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%D8%B3%D8%A7%D8%B9%D9%87_%D8%A7%D8%B3%D8%AA%D8%AC%D8%A7%D8%A8%D9%87"
       },
       {
        "tweet_volume": null,
        "query": "%23OMantoEhMeu",
        "name": "#OMantoEhMeu",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23OMantoEhMeu"
       },
       {
        "tweet_volume": 87779,
        "query": "%231YearWithMonstaX",
        "name": "#1YearWithMonstaX",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%231YearWithMonstaX"
       },
       {
        "tweet_volume": 326077,
        "query": "%E3%83%99%E3%83%83%E3%82%AD%E3%83%BC",
        "name": "\u30d9\u30c3\u30ad\u30fc",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%E3%83%99%E3%83%83%E3%82%AD%E3%83%BC"
       },
       {
        "tweet_volume": null,
        "query": "%22Darwyn+Cooke%22",
        "name": "Darwyn Cooke",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Darwyn+Cooke%22"
       },
       {
        "tweet_volume": 186028,
        "query": "%22Sexta-feira+13%22",
        "name": "Sexta-feira 13",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Sexta-feira+13%22"
       },
       {
        "tweet_volume": null,
        "query": "%22Alonso+y+Maroto%22",
        "name": "Alonso y Maroto",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Alonso+y+Maroto%22"
       },
       {
        "tweet_volume": 63014,
        "query": "Sese%C3%B1a",
        "name": "Sese\u00f1a",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=Sese%C3%B1a"
       },
       {
        "tweet_volume": null,
        "query": "%22The+Toast%22",
        "name": "The Toast",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22The+Toast%22"
       },
       {
        "tweet_volume": null,
        "query": "CPMF",
        "name": "CPMF",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=CPMF"
       },
       {
        "tweet_volume": null,
        "query": "%22Fatma+Samoura%22",
        "name": "Fatma Samoura",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Fatma+Samoura%22"
       },
       {
        "tweet_volume": 30964,
        "query": "Djokovic",
        "name": "Djokovic",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=Djokovic"
       },
       {
        "tweet_volume": 16406,
        "query": "%23SextaDetremura250Ksdv",
        "name": "#SextaDetremura250Ksdv",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23SextaDetremura250Ksdv"
       },
       {
        "tweet_volume": null,
        "query": "%23SintoSaudadeDe",
        "name": "#SintoSaudadeDe",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23SintoSaudadeDe"
       },
       {
        "tweet_volume": 20224,
        "query": "%23FANBPatriota",
        "name": "#FANBPatriota",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23FANBPatriota"
       },
       {
        "tweet_volume": 45351,
        "query": "%23%E3%81%93%E3%81%AE%E3%82%BF%E3%82%B0%E3%82%92%E3%81%BF%E3%81%9F%E4%BA%BA%E3%81%AF%E5%A5%BD%E3%81%8D%E3%81%AA%E8%8A%B1%E3%82%92%E7%AD%94%E3%81%88%E3%82%8B",
        "name": "#\u3053\u306e\u30bf\u30b0\u3092\u307f\u305f\u4eba\u306f\u597d\u304d\u306a\u82b1\u3092\u7b54\u3048\u308b",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%E3%81%93%E3%81%AE%E3%82%BF%E3%82%B0%E3%82%92%E3%81%BF%E3%81%9F%E4%BA%BA%E3%81%AF%E5%A5%BD%E3%81%8D%E3%81%AA%E8%8A%B1%E3%82%92%E7%AD%94%E3%81%88%E3%82%8B"
       },
       {
        "tweet_volume": 20336,
        "query": "%23%D8%A7%D9%84%D8%A7%D9%87%D9%84%D9%8A_%D8%A8%D8%B7%D9%84_%D8%A7%D9%84%D8%AF%D9%88%D8%B1%D9%8A_2016",
        "name": "#\u0627\u0644\u0627\u0647\u0644\u064a_\u0628\u0637\u0644_\u0627\u0644\u062f\u0648\u0631\u064a_2016",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%D8%A7%D9%84%D8%A7%D9%87%D9%84%D9%8A_%D8%A8%D8%B7%D9%84_%D8%A7%D9%84%D8%AF%D9%88%D8%B1%D9%8A_2016"
       },
       {
        "tweet_volume": 499532,
        "query": "%23FIRE2ndWin",
        "name": "#FIRE2ndWin",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23FIRE2ndWin"
       },
       {
        "tweet_volume": 36331,
        "query": "%23MasakitKapag",
        "name": "#MasakitKapag",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23MasakitKapag"
       },
       {
        "tweet_volume": 63990,
        "query": "%23%D9%85%D8%B1%D8%A7%D9%82%D8%A8_%D8%A7%D9%85%D8%A7%D9%86%D9%87_%D9%8A%D8%B5%D8%B9%D9%82_%D9%85%D9%88%D8%A7%D8%B7%D9%86",
        "name": "#\u0645\u0631\u0627\u0642\u0628_\u0627\u0645\u0627\u0646\u0647_\u064a\u0635\u0639\u0642_\u0645\u0648\u0627\u0637\u0646",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%D9%85%D8%B1%D8%A7%D9%82%D8%A8_%D8%A7%D9%85%D8%A7%D9%86%D9%87_%D9%8A%D8%B5%D8%B9%D9%82_%D9%85%D9%88%D8%A7%D8%B7%D9%86"
       },
       {
        "tweet_volume": null,
        "query": "%23QueBonito",
        "name": "#QueBonito",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23QueBonito"
       },
       {
        "tweet_volume": null,
        "query": "%23MIvKXIP",
        "name": "#MIvKXIP",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23MIvKXIP"
       },
       {
        "tweet_volume": 207161,
        "query": "%23SMTM5",
        "name": "#SMTM5",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23SMTM5"
       },
       {
        "tweet_volume": 19298,
        "query": "%23karmakar%C4%B1%C5%9F%C4%B1k",
        "name": "#karmakar\u0131\u015f\u0131k",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23karmakar%C4%B1%C5%9F%C4%B1k"
       },
       {
        "tweet_volume": 16393,
        "query": "%23jojo_anime",
        "name": "#jojo_anime",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23jojo_anime"
       },
       {
        "tweet_volume": null,
        "query": "%23%E3%83%90%E3%82%BA%E3%83%AA%E3%82%BA%E3%83%A0",
        "name": "#\u30d0\u30ba\u30ea\u30ba\u30e0",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%E3%83%90%E3%82%BA%E3%83%AA%E3%82%BA%E3%83%A0"
       },
       {
        "tweet_volume": null,
        "query": "%23FrasesDeGalanChilensis",
        "name": "#FrasesDeGalanChilensis",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23FrasesDeGalanChilensis"
       },
       {
        "tweet_volume": null,
        "query": "%23Oxxos",
        "name": "#Oxxos",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23Oxxos"
       },
       {
        "tweet_volume": 61460,
        "query": "%23%D8%AF%D8%B9%D8%A7%D8%A1_%D8%AA%D8%AA%D9%85%D9%86%D9%8A_%D9%8A%D8%B3%D8%AA%D8%AC%D8%A7%D8%A8",
        "name": "#\u062f\u0639\u0627\u0621_\u062a\u062a\u0645\u0646\u064a_\u064a\u0633\u062a\u062c\u0627\u0628",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%D8%AF%D8%B9%D8%A7%D8%A1_%D8%AA%D8%AA%D9%85%D9%86%D9%8A_%D9%8A%D8%B3%D8%AA%D8%AC%D8%A7%D8%A8"
       },
       {
        "tweet_volume": null,
        "query": "%23DontWorryBoutAThingCuz",
        "name": "#DontWorryBoutAThingCuz",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23DontWorryBoutAThingCuz"
       },
       {
        "tweet_volume": 14338,
        "query": "%23ALDUBBulagaan2016",
        "name": "#ALDUBBulagaan2016",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23ALDUBBulagaan2016"
       },
       {
        "tweet_volume": 25298,
        "query": "%23VemComOClubeLLSDV",
        "name": "#VemComOClubeLLSDV",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23VemComOClubeLLSDV"
       },
       {
        "tweet_volume": null,
        "query": "%23LaSubeNoSePresta",
        "name": "#LaSubeNoSePresta",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23LaSubeNoSePresta"
       },
       {
        "tweet_volume": null,
        "query": "%23%E6%96%87%E5%BA%AB%E5%B7%9D%E6%9F%B3",
        "name": "#\u6587\u5eab\u5ddd\u67f3",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%E6%96%87%E5%BA%AB%E5%B7%9D%E6%9F%B3"
       },
       {
        "tweet_volume": 52177,
        "query": "%23%E0%B8%A1%E0%B8%B5%E0%B8%AD%E0%B8%B0%E0%B9%84%E0%B8%A3%E0%B8%88%E0%B8%B0%E0%B8%9A%E0%B8%AD%E0%B8%81%E0%B8%84%E0%B8%99%E0%B9%86%E0%B8%99%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B9%84%E0%B8%AB%E0%B8%A1",
        "name": "#\u0e21\u0e35\u0e2d\u0e30\u0e44\u0e23\u0e08\u0e30\u0e1a\u0e2d\u0e01\u0e04\u0e19\u0e46\u0e19\u0e31\u0e49\u0e19\u0e44\u0e2b\u0e21",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%E0%B8%A1%E0%B8%B5%E0%B8%AD%E0%B8%B0%E0%B9%84%E0%B8%A3%E0%B8%88%E0%B8%B0%E0%B8%9A%E0%B8%AD%E0%B8%81%E0%B8%84%E0%B8%99%E0%B9%86%E0%B8%99%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B9%84%E0%B8%AB%E0%B8%A1"
       },
       {
        "tweet_volume": 56336,
        "query": "%23%C3%9ClkedeMatemSaraydaD%C3%BC%C4%9F%C3%BCn",
        "name": "#\u00dclkedeMatemSaraydaD\u00fc\u011f\u00fcn",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%C3%9ClkedeMatemSaraydaD%C3%BC%C4%9F%C3%BCn"
       },
       {
        "tweet_volume": 26929,
        "query": "%23PragyaPurohitLost8yrs",
        "name": "#PragyaPurohitLost8yrs",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23PragyaPurohitLost8yrs"
       },
       {
        "tweet_volume": null,
        "query": "%23FlashbackFriday",
        "name": "#FlashbackFriday",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23FlashbackFriday"
       },
       {
        "tweet_volume": null,
        "query": "%23%EB%A9%98%EC%85%98%EB%B0%9B%EC%9D%80_%EC%9E%A5%EB%A5%B4%EC%9D%98_%EC%B5%9C%EC%95%A0%EC%BA%90%EB%A5%BC_%EB%A7%90%ED%95%B4%EB%B3%B8%EB%8B%A4",
        "name": "#\uba58\uc158\ubc1b\uc740_\uc7a5\ub974\uc758_\ucd5c\uc560\uce90\ub97c_\ub9d0\ud574\ubcf8\ub2e4",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%EB%A9%98%EC%85%98%EB%B0%9B%EC%9D%80_%EC%9E%A5%EB%A5%B4%EC%9D%98_%EC%B5%9C%EC%95%A0%EC%BA%90%EB%A5%BC_%EB%A7%90%ED%95%B4%EB%B3%B8%EB%8B%A4"
       },
       {
        "tweet_volume": null,
        "query": "%23%D9%BE%D8%B1%D8%B3%D9%BE%D9%88%D9%84%DB%8C%D8%B3",
        "name": "#\u067e\u0631\u0633\u067e\u0648\u0644\u06cc\u0633",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%D9%BE%D8%B1%D8%B3%D9%BE%D9%88%D9%84%DB%8C%D8%B3"
       },
       {
        "tweet_volume": null,
        "query": "%23SnapdealDeliversFastest",
        "name": "#SnapdealDeliversFastest",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23SnapdealDeliversFastest"
       },
       {
        "tweet_volume": null,
        "query": "%23%D8%A7%D9%84%D8%B3%D8%AF_%D8%A7%D9%84%D8%B1%D9%8A%D8%A7%D9%86",
        "name": "#\u0627\u0644\u0633\u062f_\u0627\u0644\u0631\u064a\u0627\u0646",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%D8%A7%D9%84%D8%B3%D8%AF_%D8%A7%D9%84%D8%B1%D9%8A%D8%A7%D9%86"
       },
       {
        "tweet_volume": null,
        "query": "%23%D9%86%D8%AC%D9%85_%D8%A8%D8%B1%D9%82%D8%A7_100k_%D9%85%D8%AA%D8%A7%D8%A8%D8%B9",
        "name": "#\u0646\u062c\u0645_\u0628\u0631\u0642\u0627_100k_\u0645\u062a\u0627\u0628\u0639",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%D9%86%D8%AC%D9%85_%D8%A8%D8%B1%D9%82%D8%A7_100k_%D9%85%D8%AA%D8%A7%D8%A8%D8%B9"
       },
       {
        "tweet_volume": 13710,
        "query": "%23%E4%B8%8D%E6%A9%9F%E5%AB%8C%E3%81%AA%E6%9E%9C%E5%AE%9F",
        "name": "#\u4e0d\u6a5f\u5acc\u306a\u679c\u5b9f",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%E4%B8%8D%E6%A9%9F%E5%AB%8C%E3%81%AA%E6%9E%9C%E5%AE%9F"
       },
       {
        "tweet_volume": null,
        "query": "%23%D8%A7%D9%8A%D9%82%D8%A7%D9%81_%D8%A7%D9%84%D8%B1%D9%8A%D8%A7%D8%B6%D9%87_%D8%A7%D9%84%D9%83%D9%88%D9%8A%D8%AA%D9%8A%D9%87",
        "name": "#\u0627\u064a\u0642\u0627\u0641_\u0627\u0644\u0631\u064a\u0627\u0636\u0647_\u0627\u0644\u0643\u0648\u064a\u062a\u064a\u0647",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23%D8%A7%D9%8A%D9%82%D8%A7%D9%81_%D8%A7%D9%84%D8%B1%D9%8A%D8%A7%D8%B6%D9%87_%D8%A7%D9%84%D9%83%D9%88%D9%8A%D8%AA%D9%8A%D9%87"
       },
       {
        "tweet_volume": null,
        "query": "%23UnMonumentoPara",
        "name": "#UnMonumentoPara",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23UnMonumentoPara"
       },
       {
        "tweet_volume": null,
        "query": "%23Scream7Minutes",
        "name": "#Scream7Minutes",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23Scream7Minutes"
       }
      ],
      "created_at": "2016-05-13T16:20:17Z",
      "locations": [
       {
        "woeid": 1,
        "name": "Worldwide"
       }
      ],
      "as_of": "2016-05-13T16:25:28Z"
     }
    ]
    [
     {
      "trends": [
       {
        "tweet_volume": 131765,
        "query": "%23Fridaythe13th",
        "name": "#Fridaythe13th",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23Fridaythe13th"
       },
       {
        "tweet_volume": null,
        "query": "%22Darwyn+Cooke%22",
        "name": "Darwyn Cooke",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Darwyn+Cooke%22"
       },
       {
        "tweet_volume": null,
        "query": "%22The+Toast%22",
        "name": "The Toast",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22The+Toast%22"
       },
       {
        "tweet_volume": null,
        "query": "%23FlashbackFriday",
        "name": "#FlashbackFriday",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23FlashbackFriday"
       },
       {
        "tweet_volume": 15319,
        "query": "%22Stevie+Wonder%22",
        "name": "Stevie Wonder",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Stevie+Wonder%22"
       },
       {
        "tweet_volume": null,
        "query": "%23DontWorryBoutAThingCuz",
        "name": "#DontWorryBoutAThingCuz",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23DontWorryBoutAThingCuz"
       },
       {
        "tweet_volume": null,
        "query": "%22John+Miller%22",
        "name": "John Miller",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22John+Miller%22"
       },
       {
        "tweet_volume": null,
        "query": "%22Racist+McShootface%22",
        "name": "Racist McShootface",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Racist+McShootface%22"
       },
       {
        "tweet_volume": null,
        "query": "%23TravelSkills",
        "name": "#TravelSkills",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23TravelSkills"
       },
       {
        "tweet_volume": null,
        "query": "%23513Day",
        "name": "#513Day",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23513Day"
       },
       {
        "tweet_volume": null,
        "query": "%22Tommy+Joseph%22",
        "name": "Tommy Joseph",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Tommy+Joseph%22"
       },
       {
        "tweet_volume": 30254,
        "query": "Nadal",
        "name": "Nadal",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=Nadal"
       },
       {
        "tweet_volume": null,
        "query": "%22Nicole+Scherzinger%22",
        "name": "Nicole Scherzinger",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Nicole+Scherzinger%22"
       },
       {
        "tweet_volume": null,
        "query": "%22Texas+Supreme+Court%22",
        "name": "Texas Supreme Court",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Texas+Supreme+Court%22"
       },
       {
        "tweet_volume": null,
        "query": "%22Dionne+Warwick%22",
        "name": "Dionne Warwick",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Dionne+Warwick%22"
       },
       {
        "tweet_volume": null,
        "query": "%22Brandon+Ross%22",
        "name": "Brandon Ross",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Brandon+Ross%22"
       },
       {
        "tweet_volume": null,
        "query": "%22Keenan+Reynolds%22",
        "name": "Keenan Reynolds",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Keenan+Reynolds%22"
       },
       {
        "tweet_volume": null,
        "query": "%22Rory+McIlroy%22",
        "name": "Rory McIlroy",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Rory+McIlroy%22"
       },
       {
        "tweet_volume": null,
        "query": "%22Ain%27t+No+Man%22",
        "name": "Ain't No Man",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Ain%27t+No+Man%22"
       },
       {
        "tweet_volume": null,
        "query": "%22Peter+Liacouras%22",
        "name": "Peter Liacouras",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Peter+Liacouras%22"
       },
       {
        "tweet_volume": null,
        "query": "%22John+Amos%22",
        "name": "John Amos",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22John+Amos%22"
       },
       {
        "tweet_volume": null,
        "query": "%22They+Miss+Unions%22",
        "name": "They Miss Unions",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22They+Miss+Unions%22"
       },
       {
        "tweet_volume": null,
        "query": "%22Gulf+of+Mexico%22",
        "name": "Gulf of Mexico",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%22Gulf+of+Mexico%22"
       },
       {
        "tweet_volume": null,
        "query": "%23RSVPexcuses",
        "name": "#RSVPexcuses",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23RSVPexcuses"
       },
       {
        "tweet_volume": 87779,
        "query": "%231YearWithMonstaX",
        "name": "#1YearWithMonstaX",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%231YearWithMonstaX"
       },
       {
        "tweet_volume": null,
        "query": "%23NewMusicFriday",
        "name": "#NewMusicFriday",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23NewMusicFriday"
       },
       {
        "tweet_volume": null,
        "query": "%23NationalHummusDay",
        "name": "#NationalHummusDay",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23NationalHummusDay"
       },
       {
        "tweet_volume": 37487,
        "query": "%23Viernes13",
        "name": "#Viernes13",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23Viernes13"
       },
       {
        "tweet_volume": null,
        "query": "%23smbmsp90",
        "name": "#smbmsp90",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23smbmsp90"
       },
       {
        "tweet_volume": null,
        "query": "%23OMCchat",
        "name": "#OMCchat",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23OMCchat"
       },
       {
        "tweet_volume": null,
        "query": "%23MurderASongOrBand",
        "name": "#MurderASongOrBand",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23MurderASongOrBand"
       },
       {
        "tweet_volume": null,
        "query": "%23TopGunDay",
        "name": "#TopGunDay",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23TopGunDay"
       },
       {
        "tweet_volume": 33280,
        "query": "%23FreeJeanetteJing",
        "name": "#FreeJeanetteJing",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23FreeJeanetteJing"
       },
       {
        "tweet_volume": null,
        "query": "%23AskTheMayor",
        "name": "#AskTheMayor",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23AskTheMayor"
       },
       {
        "tweet_volume": null,
        "query": "%23KellyandMichael",
        "name": "#KellyandMichael",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23KellyandMichael"
       },
       {
        "tweet_volume": null,
        "query": "%23smbhou",
        "name": "#smbhou",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23smbhou"
       },
       {
        "tweet_volume": null,
        "query": "%23MyExHadItComing",
        "name": "#MyExHadItComing",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23MyExHadItComing"
       },
       {
        "tweet_volume": null,
        "query": "%23AAA400",
        "name": "#AAA400",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23AAA400"
       },
       {
        "tweet_volume": null,
        "query": "%23untoldhistories",
        "name": "#untoldhistories",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23untoldhistories"
       },
       {
        "tweet_volume": null,
        "query": "%23FunFactFriday",
        "name": "#FunFactFriday",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23FunFactFriday"
       },
       {
        "tweet_volume": null,
        "query": "%23VU2016",
        "name": "#VU2016",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23VU2016"
       },
       {
        "tweet_volume": null,
        "query": "%23cpsgrad",
        "name": "#cpsgrad",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23cpsgrad"
       },
       {
        "tweet_volume": null,
        "query": "%23IAmNotMyBeard",
        "name": "#IAmNotMyBeard",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23IAmNotMyBeard"
       },
       {
        "tweet_volume": null,
        "query": "%23microbiome",
        "name": "#microbiome",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23microbiome"
       },
       {
        "tweet_volume": null,
        "query": "%23delasoulisdead",
        "name": "#delasoulisdead",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23delasoulisdead"
       },
       {
        "tweet_volume": 499532,
        "query": "%23FIRE2ndWin",
        "name": "#FIRE2ndWin",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23FIRE2ndWin"
       },
       {
        "tweet_volume": null,
        "query": "%23schoolfinance",
        "name": "#schoolfinance",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23schoolfinance"
       },
       {
        "tweet_volume": null,
        "query": "%23VCUSSW2016",
        "name": "#VCUSSW2016",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23VCUSSW2016"
       },
       {
        "tweet_volume": null,
        "query": "%23govtday",
        "name": "#govtday",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23govtday"
       },
       {
        "tweet_volume": null,
        "query": "%23CivicsDay",
        "name": "#CivicsDay",
        "promoted_content": null,
        "url": "http://twitter.com/search?q=%23CivicsDay"
       }
      ],
      "created_at": "2016-05-13T16:20:17Z",
      "locations": [
       {
        "woeid": 23424977,
        "name": "United States"
       }
      ],
      "as_of": "2016-05-13T16:25:30Z"
     }
    ]


### 4.2. Computing the intersection of two sets of trends


```python
world_trends_set = set([trend['name'] for trend in world_trends[0]['trends']])
us_trends_set = set([trend['name'] for trend in us_trends[0]['trends']])

common_trends = world_trends_set.intersection(us_trends_set)
print(common_trends)
```

    {'#1YearWithMonstaX', '#FlashbackFriday', '#Viernes13', 'The Toast', '#DontWorryBoutAThingCuz', 'Darwyn Cooke', '#FIRE2ndWin', '#Fridaythe13th'}


## Collecting search results


```python
# XXX: Set this variable to a trending topic,
# or anything else for that matter. The example query below
# was a trending topic when this content was being developed
# and is used throughout the remainder of this chapter.

q = '#MentionSomeoneImportantForYou'

count = 100

# See https://dev.twitter.com/docs/api/1.1/get/search/tweets

search_results = twitter_api.search.tweets(q=q, count=count)
statuses = search_results['statuses']

# Iterate through 5 more batches of results by following the cursor
for _ in range(5):
    print("Length of statuses", len(statuses))
    try:
        next_results = search_results['search_metadata']['next_results']
    
    except KeyError, e: # No more results when next_results doesn't exist
        break
        
    # Create a dictionary from next_results, which has the following form:
    # ?max_id=313519052523986943&q=NCAA&include_entities=1
    kwargs = dict([ kv.split('=') for kv in next_results[1:].split("&") ])
    
    search_results = twitter_api.search.tweets(**kwargs)
    statuses += search_results['statuses']
    
# Show one sample search result by slicing the list...
print(json.dumps(statuses[0], indent=1))
```


      File "<ipython-input-12-df8a8f514e2e>", line 21
        except KeyError e: # No more results when next_results doesn't exist
                        ^
    SyntaxError: invalid syntax


