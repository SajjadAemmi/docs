---
title: st.toast
slug: /develop/api-reference/status/st.toast
description: st.toast briefly displays a toast message in the bottom-right corner
---

<Autofunction function="streamlit.toast" />

When multiple toasts are generated, they will stack. Hovering over a toast will
stop it from disappearing. When hovering ends, the toast will disappear after
four more seconds.

```python
import streamlit as st
import time

if st.button('Three cheers'):
    st.toast('Hip!')
    time.sleep(.5)
    st.toast('Hip!')
    time.sleep(.5)
    st.toast('Hooray!', icon='🎉')
```

<Cloud name="doc-status-toast1" height="300px" />

Toast messages can also be updated. Assign `st.toast(my_message)` to a variable
and use the `.toast()` method to update it. Note: if a toast has already disappeared
or been dismissed, the update will not be seen.

```python
import streamlit as st
import time

def cook_breakfast():
    msg = st.toast('Gathering ingredients...')
    time.sleep(1)
    msg.toast('Cooking...')
    time.sleep(1)
    msg.toast('Ready!', icon = "🥞")

if st.button('Cook breakfast'):
    cook_breakfast()
```

<Cloud name="doc-status-toast2" height="200px" />
