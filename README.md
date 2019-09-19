### stream-framework
---
https://github.com/tschellenbach/Stream-Framework

```py
// stream_framework/tests/feeds/aggregate_feed/notification_feed.py

class TestNotificationFeed(TestAggregatedFeed):
  feed_cls = RedisNotificationFeed
  
  def test_mark_all(self):
    self.test_feed.insert_activities(self.aggregated.activities)
    self.test_feed.add_many_aggregated([self.aggregated])
    assert len(self.test_feed[:10]) == 1
    assert len(self.test_feed.count_unseen()) == 1
    self.test_feed.mark_all()
    assert int(self.test_feed.count_unseen()) == 0
    assert int(self.test_feed.get_denormalized_count()) == 0
    
  
```

```
```

```
```


