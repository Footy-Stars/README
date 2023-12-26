# FootyStars
FootyStars: onchain football manager with real-world stakes and provable simulation.

Built with ❤️
- D K [@delken_](https://twitter.com/delken_)
- 0xVincent.eth [@0xvincent_eth](https://twitter.com/0xvincent_eth)
- bae jae kka [@BroJustKiddinn](https://twitter.com/BroJustKiddinn)
- 0xhatsume [@0xhatsume](https://twitter.com/0xhatsume)
- Zk [@zklim5389](https://twitter.com/zklim5389)

*Link to repositories: https://github.com/orgs/Footy-Stars/repositories*

## Description
FM by Sports Interactive is a fantasy football simulator with worldwide adoption, validating the demand for a life-like simulation of being a football manager. Managers can buy or sell players from the marketplace and build their own team, and pit it against teams of other managers. To win a match, besides having players with the best possible stats and attributes, managers will try to outwit each other through different tactics and configurations. 

FootyStars is the world’s first provable football simulator, paving the way for skin-in-the-game fantasy football matches involving real-world stakes. For the first time ever, fantasy football is no longer just a game — it finally becomes a true football manager simulator:

- Provable simulation: match results are “trustless”, aka anyone can verify whether the simulation is executed properly by checking it against the generated ZKP from offchain zkML.
- Real-world stakes: the ability of FootyStars to provide trustless match results means that it would now be conducive enough for skin-in-the-game matches involving real-world money.
- Open NFT-driven player economy: player cards are no longer locked within the “walled garden” of the game developer, as each player in FootyStars are ERC721s (which means managers can trade them as easily as PFP NFTs like BAYC, or even use them to participate in DeFi).
- Player cards as investable collectibles: player ratings are determined by the player’s real-world performance (through a transparent algorithm, where an external oracle that aggregates data from multiple sports data providers like Opta / Squawka will act as the data source) as well as the DAO-elected FootyStars juries, democratizing the power of rating player cards to the masses (which enhances the investability of FootyStars player cards, since no central entity holds command on the ratings of any player card NFT).

## How It's Made
The core of our product is EZKL — we use it to run our offchain football match simulator and return a ZKP onchain to prove that the provided inputs from both managers are executed correctly within this “global” model. Please refer to our GitHub repo for more details.

As with a football game, the best team doesn’t always win. There’s an element of luck involved that could swing a match’s results in favor of the lesser team. Here, we use API3’s QRNG to mimic the real-world’s “luck factor”: under certain probability distributions, a supposed 2-1 win for team A (as simulated by the EZKL model) might become a 2-2 draw.

FootyStars managers may scout the patterns of other managers prior to a match, such that they can conjure up the most appropriate strategy (player composition, tactics, etc.) to win their match against this particular manager. We have created our own Subgraph to index match histories (score results and manager inputs) and display it on the front-end in a user-friendly interface.

To store NFT metadata (player profile: biodata, stats, etc.), we leverage IPFS via NFT.Storage. In addition, we will periodically store manager inputs of long-dated historical matches on IPFS.
