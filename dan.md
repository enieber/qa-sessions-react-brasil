# QA-sessions With  [Dan Abramov]()
## Data: 14/04/2018 (15:00-14:00)

### Vinicius Rangel [2:01 PM]
Dan, there are bigger plans to redux this year?

> Not sure what you mean :slightly_smiling_face: But I have no plans regarding Redux personally. I'm not actively involved with maintaining it.

### thiago.leite [2:02 PM]
Andrew Clark said on his Twitter that class components will be considered as legacy APIs in the future, while function components will remain. We must take this statement in consideration in the projects that are under development/will be developed? And what is the best way to write a component?

> He also said on Twitter that we have dozens of thousands of class components and they aren't going anywhere :slightly_smiling_face: When/if we have a more convenient and less verbose way to declare components than classes, we'll definitely announce it, but I don't see how it could affect existing projects.

### pvieira91 [2:00 PM]
Tests | We went from 0 to 100 in what regards unit testing. It’s pretty common nowadays to find companies that have very high thresholds on unit testings. Do you think that it’s valuable to impose a high unit test coverage even for presentational components?

> Personally I don't find unit testing components very valuable. Especially if they just contain markup — you're basically testing that React works, and we have tests in React itself for that. I think some combination of integration tests for higher-level UI scenarios (click a button, something shows up) and unit tests for _logic_ (e.g. complex calculations) is helpful. I'm more skeptical of asserting on component output although I understand others might not agree.


### pvieira91 [2:00 PM]
Styling | What is your opinion of css-in-js? Do you prefer it over standard stylesheets (scss, css-modules, post-css etc) or it’s more interesting to use a css-in-js lib? If so, which one? (styled-components)?

> I don't care about this much. If I were writing something today for myself I'd probably use vanilla CSS. Maybe glamor if there were a lot of dynamic styles.

### sibelius [2:03 PM]
how will async react help in handling requests waterfall?

> Not sure what exactly is being asked. But my guess is this is about the case where you have a parent and child component that each request some data, but it could've been requested in parallel.With “suspense” APIs (part of async React), we think it’s much simpler to “move” async dependencies up and down the tree without re-wiring the props or changing the app architecture. This is because all components are backed by the same cache. So I think async React would help avoid waterfalls by making it easier to optimistically _preload_ resources that you think components below will need. Similar to `<link rel="preload">` in HTML.

### sibelius [2:03 PM]
how will async react improve react native?

> There's work in progress on revamping React Native architecture to better take advantage of async rendering and solving some existing pain points regarding interop with sync code. I’m not the best person to talk about that though.

### sibelius [2:03 PM]
what is take on flow/typescript and reason?

> I’m personally comfortable with JS + some sprinkles of Flow where I’m not confident what’s going on with types. Not a fan of having to annotate everything. I haven’t tried Reason yet so I don’t know if I’ll like it.

### sibelius [2:03 PM]
what next after relay modern?

> I don’t know, is there something missing in it? My understanding is that the Relay team is happy with performance wins from Modern. We might need to change the React bindings to it to better take advantage of the upcoming React async features, but I don’t know more.

