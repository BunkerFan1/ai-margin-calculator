# Product Requirements Document
## AI Product Margin Calculator

### Executive Summary
A free, no-signup web tool that enables AI product teams to calculate and visualize their gross margins per customer based on model usage patterns, pricing models, and operational overhead. The calculator reveals hidden cost dynamics, particularly where subscription pricing becomes unprofitable due to agentic looping behaviors.

### Problem Statement
AI product companies struggle to understand unit economics because:
- Model costs vary dramatically by provider, model size, and caching strategies
- Customer usage patterns are unpredictable, especially with autonomous agents
- Traditional SaaS pricing models break down when compute costs scale with usage
- Multi-turn agentic workflows can create runaway costs that aren't visible until month-end
- Teams lack visibility into which customer segments are profitable vs. underwater

### Target Users
**Primary:** 
- AI product managers setting pricing strategy
- Finance teams modeling unit economics
- Engineering leaders evaluating model selection trade-offs

**Secondary:**
- Founders/executives making go-to-market decisions
- Sales teams needing to understand pricing boundaries
- Investors evaluating AI startup economics

### Core Features

#### 1. Model Mix Configuration
**Input Parameters:**
- Model provider selection (OpenAI, Anthropic, Google, Mistral, Llama, custom)
- Model tier distribution (% GPT-4o vs GPT-4o-mini, Claude Sonnet vs Haiku, etc.)
- Custom model pricing override option
- Blended cost per million tokens (input/output separately)

**Requirements:**
- Pre-populated with current pricing for major providers
- Visual slider for model mix percentages
- Real-time blended cost calculation
- Import/export model configurations

#### 2. Usage Pattern Inputs
**Token Volume Metrics:**
- Average tokens per user per month (input/output)
- Token growth rate month-over-month
- Peak vs. average usage multiplier
- User segmentation (power users vs. casual)

**Caching Configuration:**
- Cached vs. uncached request ratio
- Cache hit rate percentage
- Prompt caching savings calculator
- Context caching effectiveness

**Agentic Overhead:**
- Average turns per conversation
- Agent loop detection threshold
- Recursive call multiplier
- Tool use token overhead
- System prompt token cost

#### 3. Pricing Model Builder
**Subscription Tiers:**
- Seat-based pricing (per user per month)
- Tiered seat pricing with volume discounts
- Feature-gated tiers with different token allowances

**Usage-Based Options:**
- Credit packages (pre-paid blocks)
- Pay-as-you-go with markup
- Hybrid (base seat + overage)
- Token allowance per tier

**Advanced Pricing:**
- Commitment discounts
- Enterprise negotiated rates
- Freemium token limits

#### 4. Margin Analysis Dashboard

**Per-Customer Metrics:**
- Gross margin per customer segment
- Break-even analysis by usage level
- Contribution margin after infrastructure
- LTV:CAC implications of margin profile

**Cohort Analysis:**
- Profitable vs. underwater customer identification
- Usage distribution histogram with profitability overlay
- Power user impact on blended margins
- Margin degradation from agentic loops

**Scenario Modeling:**
- "What-if" agent loop frequency increases
- Price sensitivity analysis
- Model mix optimization suggestions
- Margin impact of switching providers

**Visual Outputs:**
- Heat map: usage vs. margin by customer segment
- Break-even frontier visualization
- Loop detection warning zones
- Margin waterfall from list price to gross margin

#### 5. Advanced Features

**Loop Detection Simulator:**
- Define agent behavior patterns
- Simulate runaway loop scenarios
- Calculate worst-case margin impact
- Suggest rate limiting thresholds

**Optimization Recommendations:**
- Identify optimal model mix for margin targets
- Suggest pricing adjustments by tier
- Recommend usage caps or rate limits
- Caching strategy improvements

**Export & Sharing:**
- Generate PDF/PNG reports
- Shareable link (no signup required)
- CSV export of calculations
- API for embedding in internal tools

### Non-Functional Requirements

**Performance:**
- All calculations update in <100ms
- Support 1000+ customer segments
- Handle complex pricing models without lag

**Usability:**
- Zero friction: no signup, login, or email required
- Mobile-responsive design
- Keyboard navigation support
- Tooltips explaining each parameter
- Pre-filled with realistic example data

**Data & Privacy:**
- All calculations client-side (no server storage)
- Optional browser local storage for saving scenarios
- No tracking or analytics on user inputs
- Clear data privacy statement

### Success Metrics
- 10,000+ unique users in first 3 months
- Average session duration >5 minutes
- 25% of users run multiple scenarios
- Organic sharing rate >15%
- Becomes referenced tool in pricing discussions

### Technical Implementation Notes
- Pure client-side React/Next.js application
- Recharts or D3.js for visualizations
- Local storage for saving configurations
- Deployed on Vercel/Netlify (static hosting)
- Optional: Embed as widget in other tools

### Launch Strategy
- Initial version with core calculators
- Beta feedback from 10 design partners
- Launch on Product Hunt, Hacker News
- Content marketing: "Hidden costs of AI products"
- Open source calculation methodology

### Future Enhancements (Post-Launch)
- Multi-model routing optimization
- Fine-tuning cost calculator
- Infrastructure overhead calculator
- Team collaboration features (with accounts)
- Industry benchmark data
- Real-time model pricing API integration
- Monte Carlo simulation for usage patterns
- P&L projection beyond gross margin