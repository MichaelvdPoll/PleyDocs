## Pley Firebase

### Step 4: Access Firebase in your game

Code snippet contains incorrect namespace


```cs
#if UNITY_WEBGL && !UNITY_EDITOR
using Trail.Firebase;
using Trail.Firebase.Analytics;
using Trail.Firebase.Extensions;
#else
using Firebase;
using Firebase.Analytics;
using Firebase.Extensions;
#endif

....

void OnLevelUp(int newLevel)
{
    FirebaseAnalytics.LogEvent(FirebaseAnalytics.EventLevelUp, FirebaseAnalytics.ParameterLevel, newLevel);
}
```

