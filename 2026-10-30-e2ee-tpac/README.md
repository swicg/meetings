# ActivityPub E2EE TPAC 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Martin Thomson
- Aaron Coburn
- David Roetzel
- Darius Kazemi
- Bert Bos (W3C)


## Agenda

- Introductions
- COC and CLA
- Share information about E2EE messaging in ActivityPub (EP)
- Collect feedback for next steps

## Notes

Opening presentation from Evan:

https://docs.google.com/presentation/d/1WVnwDAozCu5_uRKazZLkkHVG3mAqP7sRFq53Xt3WlL4/edit?slide=id.h4a2db28042828ddf_0_5#slide=id.h4a2db28042828ddf_0_5

### Discussion

Some discussion of whether this stays as a CG Report, or goes into the Social Web WG.

Martin: You probably want to bring this into the WG because it triggers a bunch of protections that the W3C is designed to give. You might even consider a "rotating CR" goal for this spec, where you publish a Candidate Recommendation, and then continue updating it as you figure out the large file problems and so on.

Darius: That matches my sense, this work seems important enough that it needs the W3C protections and reviews. I'll work with Team to figure out if our charter allows for bringing it in or if we'd need a recharter.

Evan: I wanted to discuss interop. We have a content model of ActivityStreams. There's another model called MIMI. I think it's reasonable for AP implementers to use a dual content model if they want to interop with MIMI content. It's much easier for AP devs to use our native structures but it's possible.

David: You mentioned a UX issue which was key comparison. There are other UX issues - did you consider other UX issues? We are talking about interoperability in a very sensitive area. It might be important to set some UX standards and expectations.

Evan: One big one in this area since we are building e2ee on systems that already have unencrypted private messaging is to keep those systems strictly separated. One temptation is to mix the two systems together but we  need to keep them completely separate.

Martin: THere's key comparison, but that's a last resort. You should look very seriously into public ledgers of keys, key transparency.

bumblefudge: This was referred to in the presentation as a registry but that was a key transparency registry. soatoak has been pressing for this - key transparency registries help ensure the keys [sorry, scribe lost this].

Martin: Yes, you have 40k servers, each server can work with a registry and have transparency logs for each one of those servers on the registry. It's not that hard to set up, but harder to govern. There's a ton of work to be done on the key management side of things, but baby steps.

Evan: in this area it's hard to tell when the perfect is the enemy of the good, or when good enough is definitely not good enough. We are trying to separate out what can wait for extensions and what needs to be core. We are trying to strictly following the MLS model at the core. I don't want to stray too far from that model and learn difficult lessons on our own.

Evan: Also we are working towards a federated implementation of MLS, which is not unique but is pretty cool. It's nice that we are getting it done and pushing some boundaries on MLS too.

Anne: https://github.com/mozilla/mls-webapi-explainer - this is something FIrefox has been working on that's related
