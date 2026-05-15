# CommuniEats: Community-Powered Last-Mile Delivery

Rethinking last-mile delivery through community collaboration

## Executive Summary

CommuniEats is a live marketplace that reimagines delivery economics by offering customers three fulfillment options with corresponding discounts. By matching orders with neighbors already traveling to that area, CommuniEats reduces delivery costs for everyone while leveraging existing neighborhood travel patterns.

## The Problem

**Delivery fees are economically broken.**

A $42 meal costs customers $56 after fees—a 33% markup for a single dedicated trip. The root issue isn't the fee itself; it's the model:

**Every order creates its own trip. Every trip requires its own courier.**

This means platforms create redundant transportation even when neighbors are already traveling those exact routes. The solution isn't better logistics—it's better collaboration.

## The Solution: Three-Tier Fulfillment Model

CommuniEats lets customers choose how they want their order fulfilled, with pricing that rewards community participation:

### 1. Traditional Delivery
- **What**: Full-service courier handles pickup and delivery
- - **Cost**: Full price (0% discount)
  - - **Best for**: Convenience-first customers
    - - **Community impact**: Creates dedicated delivery trip
     
      - ### 2. Self-Pickup
      - - **What**: You pick up your order directly from the restaurant
        - - **Cost**: 10% discount
          - - **Best for**: Budget-conscious local shoppers
            - - **Community impact**: Zero delivery footprint
             
              - ### 3. Community Pickup ⭐ *The Core Innovation*
              - - **What**: A neighbor in your area picks up your order while running their own errands
                - - **Cost**: 30% discount
                  - - **How it works**:
                    -   - System identifies neighbors heading to that area
                        -   - Shows you available community delivery partners
                            -   - Neighbor picks up your order on their route
                                -   - You both save money
                                    - - **Best for**: Cost-saving customers in active neighborhoods
                                      - - **Community impact**: Eliminates wasteful dedicated trips
                                       
                                        - ## How It Works: The Community Pickup Flow
                                       
                                        - ```
                                          1. Customer selects their fulfillment preference at checkout
                                             ↓
                                          2. System displays available delivery options + pricing
                                             • Traditional Delivery: $42.00
                                             • Self Pickup: $37.80 (10% off)
                                             • Community Pickup: $29.40 (30% off) ← Available neighbors shown here
                                             ↓
                                          3. If Community Pickup selected:
                                             • Shows list of neighbors heading to your area
                                             • Displays neighbor profile & availability window
                                             ↓
                                          4. Neighbor accepts the delivery
                                             • Picks up your order on their existing route
                                             • Delivers to your location
                                             ↓
                                          5. Order complete
                                             • You save 30%
                                             • Neighbor gets a small incentive
                                             • One less delivery truck on the road
                                          ```

                                          ## Product Features (Live)

                                          ✅ **Dynamic pricing by fulfillment method**
                                          - Real-time discount calculation
                                          - - Transparent cost breakdown at checkout
                                            - - Automatic savings calculation
                                             
                                              - ✅ **Neighbor availability matching**
                                              - - Shows community delivery partners in your area
                                                - - Displays delivery timeframe
                                                  - - Neighbor profile information
                                                   
                                                    - ✅ **Three fulfillment mode toggle**
                                                    - - Seamless switching between options
                                                      - - Instant price recalculation
                                                        - - Visual comparison of discounts
                                                         
                                                          - ✅ **Configuration-driven UI**
                                                          - - No custom design required
                                                            - - Rapid deployment and iteration
                                                              - - Solo-developer friendly architecture
                                                               
                                                                - ## Why This Works
                                                               
                                                                - ### The Economics
                                                                - | User Type | Motivation |
                                                                - |-----------|-----------|
                                                                - | **Budget-conscious customers** | Save 30% on their order |
                                                                - | **Neighbors delivering** | Get incentivized for their existing trip |
                                                                - | **Platform** | Reduce delivery infrastructure costs |
                                                                - | **Environment** | Fewer redundant vehicles on roads |
                                                               
                                                                - ### The Insight
                                                                - Neighbors aren't strangers with delivery apps—they're already traveling. CommuniEats simply **coordinates existing trips rather than creating new ones**.
                                                               
                                                                - ## Tech Stack
                                                               
                                                                - ### Frontend
                                                                - - **Framework**: Next.js with React
                                                                  - - **Language**: TypeScript
                                                                    - - **Styling**: Tailwind CSS
                                                                      - - **UI Pattern**: Configuration-based components (no custom design)
                                                                       
                                                                        - ### Backend
                                                                        - - **Compute**: Vercel Functions
                                                                          - - **API**: Next.js API Routes
                                                                            - - **Matching Logic**: Geolocation-based neighbor correlation
                                                                             
                                                                              - ### Infrastructure & Database
                                                                              - - **Deployment**: Vercel (Edge network)
                                                                                - - **Database**: PostgreSQL/MongoDB (configurable)
                                                                                  - - **Maps/Geolocation**: Real-time location services
                                                                                    - - **Payment**: Stripe integration for discount processing
                                                                                     
                                                                                      - ## Architecture Overview
                                                                                     
                                                                                      - ```
                                                                                        CommuniEats/
                                                                                        ├── components/
                                                                                        │   ├── Checkout/
                                                                                        │   │   ├── FulfillmentModeSelector.tsx    # Toggle between 3 options
                                                                                        │   │   ├── PricingDisplay.tsx             # Shows discount breakdown
                                                                                        │   │   └── NeighborAvailability.tsx       # Lists nearby delivery partners
                                                                                        │   ├── DeliveryMap/
                                                                                        │   │   └── NeighborLocation.tsx           # Real-time tracking
                                                                                        │   └── UI/                                # Config-driven components
                                                                                        │
                                                                                        ├── pages/
                                                                                        │   ├── checkout.tsx                       # Fulfillment mode selection
                                                                                        │   ├── api/
                                                                                        │   │   ├── matching/neighbors.ts          # Find neighbors in area
                                                                                        │   │   ├── pricing/calculate.ts           # Discount calculation
                                                                                        │   │   └── orders/create.ts               # Order placement
                                                                                        │   └── delivery.tsx                       # Active order tracking
                                                                                        │
                                                                                        ├── lib/
                                                                                        │   ├── geolocation/                       # Distance calculation
                                                                                        │   ├── matchmaking/                       # Neighbor-to-order correlation
                                                                                        │   └── pricing/                           # Discount logic
                                                                                        │
                                                                                        ├── config/
                                                                                        │   ├── discounts.json                     # 0%, 10%, 30% discount tiers
                                                                                        │   └── ui-config.json                     # Component configuration
                                                                                        │
                                                                                        └── styles/                                # Tailwind CSS
                                                                                        ```

                                                                                        ## Product Research & Unanswered Questions

                                                                                        While the core product is live, several important questions remain being explored:

                                                                                        ### Trust Problem
                                                                                        - How do we ensure neighbor reliability and food safety?
                                                                                        - - What happens when an order goes wrong?
                                                                                          - - How do we handle disputes fairly?
                                                                                           
                                                                                            - ### Density Problem
                                                                                            - - Does this work in suburban/rural areas with lower population density?
                                                                                              - - What's the minimum user density needed for viable neighbor matching?
                                                                                               
                                                                                                - ### Timing Problem
                                                                                                - - Can we reliably match neighbor routes with order requests in real-time?
                                                                                                  - - How do we handle urgent orders with limited neighbor availability?
                                                                                                   
                                                                                                    - ### Incentive Problem
                                                                                                    - - Is the current discount structure sustainable?
                                                                                                      - - Do neighbors need additional incentives beyond helping their community?
                                                                                                       
                                                                                                        - ## Market Context
                                                                                                       
                                                                                                        - **JoyRun (2017)** proved this model was viable, raising $10M Series A with 2M+ users before acquisition by Walmart in 2020. Yet neighbor-powered delivery remains absent from mainstream consumer apps, suggesting the barrier isn't technology—it's solving one of the problems above at scale.
                                                                                                       
                                                                                                        - ## Getting Started
                                                                                                       
                                                                                                        - ### Prerequisites
                                                                                                       
                                                                                                        - ```
                                                                                                          Node.js >= 18.0.0
                                                                                                          npm >= 9.0.0
                                                                                                          ```
                                                                                                          
                                                                                                          ### Installation
                                                                                                          
                                                                                                          ```bash
                                                                                                          git clone https://github.com/Jgupta14051994/Communityeats.git
                                                                                                          cd Communityeats
                                                                                                          npm install
                                                                                                          ```
                                                                                                          
                                                                                                          ### Development
                                                                                                          
                                                                                                          ```bash
                                                                                                          npm run dev
                                                                                                          # Open http://localhost:3000
                                                                                                          ```
                                                                                                          
                                                                                                          ### Production Deployment
                                                                                                          
                                                                                                          ```bash
                                                                                                          npm run build
                                                                                                          npm start

                                                                                                          # Or deploy to Vercel (recommended)
                                                                                                          vercel deploy
                                                                                                          ```
                                                                                                          
                                                                                                          ## Live Product
                                                                                                          
                                                                                                          **Try it now**: [communieats-app.vercel.app](https://communieats-app.vercel.app)
                                                                                                          
                                                                                                          **Pro tip**: The fulfillment mode toggle at checkout is where the entire product mechanic lives. Try switching between Traditional Delivery → Self Pickup → Community Pickup to see the discount structure in action.
                                                                                                          
                                                                                                          ## What Makes This Different
                                                                                                          
                                                                                                          1. **Configuration over custom design** - Entire UI driven by config files, enabling solo development
                                                                                                          2. 2. **Real product, real discounts** - Not a mockup; actual checkout with live pricing
                                                                                                             3. 3. **Problem exploration focus** - The code matters less than solving trust/density/timing challenges
                                                                                                                4. 4. **Built with Claude Code** - Entire product partner approach (no dedicated designer)
                                                                                                                  
                                                                                                                   5. ## Contributing & Feedback
                                                                                                                  
                                                                                                                   6. We're looking for perspectives from people who've worked on:
                                                                                                                   7. - Marketplace incentive design
                                                                                                                      - - Last-mile logistics
                                                                                                                        - - Community-driven commerce
                                                                                                                          - - P2P transaction trust systems
                                                                                                                           
                                                                                                                            - **Key questions we'd love your input on:**
                                                                                                                            - - Which problem (trust/density/timing/incentives) is the biggest blocker?
                                                                                                                              - - Have you seen this model work elsewhere?
                                                                                                                                - - What would make you trust a neighbor with your food order?
                                                                                                                                 
                                                                                                                                  - **How to contribute:**
                                                                                                                                  - - [Open an Issue](https://github.com/Jgupta14051994/Communityeats/issues) - Report bugs or request features
                                                                                                                                    - - [GitHub Discussions](https://github.com/Jgupta14051994/Communityeats/discussions) - Debate the business model
                                                                                                                                      - - Email feedback to: **Jyotirgupta@gmail.com**
                                                                                                                                       
                                                                                                                                        - ## Contact & Resources
                                                                                                                                       
                                                                                                                                        - | Channel | Contact |
                                                                                                                                        - |---------|---------|
                                                                                                                                        - | **Product Questions** | [GitHub Issues](https://github.com/Jgupta14051994/Communityeats/issues) |
                                                                                                                                        - | **Strategy Discussion** | [GitHub Discussions](https://github.com/Jgupta14051994/Communityeats/discussions) |
                                                                                                                                        - | **Live App** | [communieats-app.vercel.app](https://communieats-app.vercel.app) |
                                                                                                                                        - | **Email** | Jyotirgupta@gmail.com |
                                                                                                                                        - | **LinkedIn** | [Jyoti Gupta](https://linkedin.com/in/jyotigupta) |
                                                                                                                                       
                                                                                                                                        - ## Important Note
                                                                                                                                       
                                                                                                                                        - This repository documents both **product thinking and working code**. The three-tier fulfillment mechanic with discounts is fully functional. However, deeper questions about trust, density, and timing remain open research problems. See [DECISION_LOG.md](DECISION_LOG.md) for detailed exploration of these challenges.
                                                                                                                                       
                                                                                                                                        - ## License
                                                                                                                                       
                                                                                                                                        - MIT License - See LICENSE for details
                                                                                                                                       
                                                                                                                                        - ---
                                                                                                                                        
                                                                                                                                        **Built**: Solo development with Claude Code partnership
                                                                                                                                        **Live Since**: May 15, 2026
                                                                                                                                        **Status**: Active product with ongoing research
                                                                                                                                        **Your Email**: Jyotirgupta@gmail.com
                                                                                                                                        
