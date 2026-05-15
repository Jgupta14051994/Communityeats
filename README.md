# CommuniEats

> **Rethinking last-mile delivery through community collaboration**
>
> ## The Problem
>
> Delivery fees are broken. A $42 dinner costs $56 after fees ($14 markup). But the real problem isn't the fee—it's the model.
>
> **The Core Issue:** Every delivery order creates its own trip. Every trip requires its own courier. Platforms batch orders between couriers, but someone still has to make that individual trip.
>
> What if the trip was *already happening*?
>
> ## The Insight
>
> Neighbors are already traveling home from restaurants, work, and shops. What if they could pick up a neighbor's order on the way home and save them 30%? Win-win.
>
> This repo documents the exploration of a **three-mode fulfillment model**:
>
> 1. **Traditional Delivery** - Full service, standard fees
> 2. 2. **Self Pickup** - You grab your own order, maximum savings
>    3. 3. **Neighbor Pickup** - A neighbor delivers on their route, ~30% discount for both
>      
>       4. ## Live Product
>      
>       5. **Try it:** [communieats-app.vercel.app](https://communieats-app.vercel.app)
>      
>       6. 👉 **Pro tip:** Check out the delivery mode toggle at checkout—that's where the core mechanic lives.
>
> ## Product Research & Decision Log
>
> ### Key Questions Being Explored
>
> 1. **Trust Problem** - What happens when a neighbor's order goes wrong? How do we handle disputes?
> 2. 2. **Density Problem** - Does this work in suburban areas? What's the minimum user density needed?
>    3. 3. **Timing Problem** - Can we reliably match neighbor routes with order requests in real-time?
>       4. 4. **Incentive Problem** - Is 30% off enough? Do neighbors need additional incentives?
>         
>          5. ### Decision Iterations
>         
>          6. #### Decision: Trust Framework for Neighbor Fulfillment
>          7. **Problem:** Neighbor-to-neighbor pickup introduced new failure modes (food quality, tamper concerns, lost orders).
>         
>          8. **Iterations:**
> 1. **V1 (Rejected):** Direct P2P payment - Too risky, no intermediary to handle disputes
> 2. 2. **V2 (Rejected):** Escrow-based release - Complicated UX, required rating before payment
>    3. 3. **V3 (Current):** Platform holds payment, releases on confirmation + photos of pickup
>       4.    - Neighbor takes photo of handed-off order
>             -    - Recipient confirms delivery or disputes within 2 hours
>                  -    - Platform releases payment or auto-refunds
>                   
>                       - **Why it took 3 iterations:** Framing trust as a *sequence of confirmations* rather than a single trust decision was the breakthrough.
>                   
>                       - ### Market Context
>                   
>                       - **JoyRun (2017)** - Similar model, raised $10M Series A, acquired by Walmart in 2020.
> - Status: Still not mainstream in consumer apps
> - - Key learning: The app is easy; the problem underneath is hard
>  
>   - This suggests the challenge is **not** product-market fit execution, but rather solving one of the three core problems above.
>  
>   - ## How It Was Built
>  
>   - - **Spec:** Built entirely with Claude Code as product partner
>     - - **Design:** No dedicated designer—configuration-based UI
>       - - **Dev Team:** Solo build to validate the mechanic
>         - - **Stack:** Next.js, TypeScript, Vercel
>          
>           - **Takeaway:** The hard part wasn't shipping the app. It was articulating the trust problem clearly enough to design a solution.
>          
>           - ## Tech Stack
>          
>           - - **Frontend:** Next.js, React, TypeScript, Tailwind CSS
> - **Backend:** Vercel Functions, Next.js API routes
> - - **Database:** [Add your DB choice]
>   - - **Deployment:** Vercel
>     - - **Maps/Routing:** [Add your choice]
>      
>       - ## Architecture Overview
>      
>       - ```
>         CommuniEats/
>         ├── components/        # UI components
>         ├── pages/            # Next.js routes
>         │   ├── checkout.tsx  # Fulfillment mode selection
>         │   └── delivery.tsx  # Delivery tracking
>         ├── lib/              # Business logic
>         │   ├── matchmaking/  # Neighbor matching algorithm
>         │   ├── trust/        # Payment & trust verification
>         │   └── validation/   # Order validation
>         └── styles/           # Global styles
>         ```
>
> ## Getting Started
>
> ### Prerequisites
> ```bash
> node >= 18.0.0
> npm >= 9.0.0
> ```
>
> ### Installation
> ```bash
> git clone https://github.com/Jgupta14051994/Communityeats.git
> cd Communityeats
> npm install
> ```
>
> ### Running Locally
> ```bash
> npm run dev
> ```
> Open [http://localhost:3000](http://localhost:3000)
>
> ### Deployment
> ```bash
> npm run build
> npm start
> ```
>
> ## Contributing & Feedback
>
> If you've worked on:
> - **Marketplace incentives**
> - - **Last-mile logistics**
>   - - **Community-driven commerce**
>     - - **Trust models for P2P transactions**
>      
>       - I'd genuinely love your perspective on:
>       - - Which problem (trust/density/timing) is the biggest blocker?
>         - - Have you seen this solved elsewhere?
>           - - What are the incentive dynamics at play?
>            
>             - **Open an issue or discussion** with your thoughts.
>            
>             - ## License
>            
>             - MIT License - see LICENSE file for details
>
> ## Contact & Social
>
> - **Product Questions:** [Open an Issue](../../issues)
> - - **Discuss the Problem:** [GitHub Discussions](../../discussions)
>   - - **Live Product:** [CommuniEats App](https://communieats-app.vercel.app)
>     - - **Email:** jyoti@communieats.dev
>       - - **LinkedIn:** [Jyoti Gupta](https://linkedin.com/in/jyotigupta)
>        
>         - ---
>
> > **Note:** This repo documents the *product thinking*, not just the code. If you're here for the business model exploration, check out the [DECISION_LOG.md](DECISION_LOG.md) file and the issues labeled `product-thinking`.
