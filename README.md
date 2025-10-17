# Baney Brew - Social Beer Rating Platform

<div align="center">

![Baney Brew Logo](https://imgur.com/a/baney-brew-logo-l6aeYBb)

**Discover, rate, and share your favorite craft beers**

[![API Status](https://img.shields.io/badge/API-Live-success)](https://api.baneybrew.com)
[![Go Version](https://img.shields.io/badge/Go-1.21+-00ADD8?logo=go&logoColor=white)](https://go.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0+-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![Rust](https://img.shields.io/badge/Rust-1.75+-000000?logo=rust&logoColor=white)](https://www.rust-lang.org)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-1.28+-326CE5?logo=kubernetes&logoColor=white)](https://kubernetes.io)
[![Azure](https://img.shields.io/badge/Azure-AKS-0078D4?logo=microsoftazure&logoColor=white)](https://azure.microsoft.com)

[Website](https://baneybrew.com) • [API Documentation](https://developers.baneybrew.com/docs) • [Request API Access](#-api-access)

</div>

---

## 🍺 About Baney Brew

Baney Brew is a next-generation social platform for beer enthusiasts, breweries, and craft beer lovers. We combine advanced flavor profiling, machine learning-powered recommendations, and real-time social features to create the ultimate beer discovery experience.

### What Makes Us Different

- **🎯 Flavor Profiling**: Proprietary 14-question taste questionnaire maps every beer onto a 4-quadrant flavor chart
- **🤖 Smart Recommendations**: Hybrid content-based and collaborative filtering powered by high-performance Rust algorithms
- **🏭 Brewery Verification**: Integrated with OpenBreweryDB for authentic brewery listings and verified ownership
- **📸 Automated Image Indexing**: ML-powered web crawlers automatically source and validate beer labels
- **💬 Real-Time Social**: WebSocket-powered messaging with live typing indicators and presence tracking
- **📊 Advanced Analytics**: Detailed insights for brewery owners on ratings, engagement, and customer preferences

---

## 🏗️ Architecture

Baney Brew is built on a modern, cloud-native architecture designed for scale, performance, and reliability.

### Technology Stack

```
┌──────────────────────────────────────────────────────────┐
│                     Frontend Layer                        │
│    TypeScript • React • Next.js 14 • TailwindCSS         │
│              Server Components • Streaming                │
└──────────────────────────────────────────────────────────┘
                            ▼
┌──────────────────────────────────────────────────────────┐
│                      API Gateway                          │
│           Go 1.21+ • Chi Router • OpenAPI 3.0            │
│        JWT Auth • Rate Limiting • Request Validation     │
└──────────────────────────────────────────────────────────┘
                            ▼
┌──────────────────────────────────────────────────────────┐
│                   Compute Layer                           │
│      Rust • High-Performance Algorithm Processing        │
│   Recommendation Engine • Popularity Scoring • Vectors   │
└──────────────────────────────────────────────────────────┘
                            ▼
┌──────────────────────────────────────────────────────────┐
│                 Infrastructure Layer                      │
│      Azure AKS • Blob Storage • MySQL • Redis            │
│         Kubernetes • Horizontal Pod Autoscaling          │
└──────────────────────────────────────────────────────────┘
```

### Why This Stack?

| Technology | Purpose | Why We Chose It |
|------------|---------|----------------|
| **Go** | REST API & WebSocket Server | Fast, reliable, excellent concurrency support for real-time features |
| **TypeScript** | Frontend & Type Safety | End-to-end type safety, excellent DX, React ecosystem |
| **Rust** | Algorithm Processing | Maximum performance for compute-intensive recommendation algorithms |
| **Azure AKS** | Container Orchestration | Enterprise-grade Kubernetes, seamless Azure integration |
| **Blob Storage** | Object Storage | Cost-effective, scalable storage for images and static assets |

---

## 🚀 Features

### For Beer Enthusiasts

- **Intelligent Search**: Find beers by name, style, brewery, ABV, IBU, or flavor profile
- **Visual Flavor Chart**: Explore beers on an interactive 4-quadrant taste map
- **Personalized Recommendations**: Get beer suggestions based on your rating history
- **Social Feed**: Follow friends, share tastings, and discuss your favorite brews
- **Direct Messaging**: Chat in real-time with other beer lovers
- **Achievements**: Earn badges for milestones like "First Review" and "Taste Explorer"

### For Breweries

- **Verified Profiles**: Claim and verify your brewery with OpenBreweryDB integration
- **Beer Management**: Add, update, and manage your beer portfolio
- **Analytics Dashboard**: Track ratings, views, and engagement metrics
- **Subscription Tiers**: Flexible plans from Free to Enterprise with API access
- **Image Automation**: Automatic label sourcing and optimization
- **Customer Insights**: Understand what your customers love about your beers

### For Developers

- **RESTful API**: Clean, well-documented API with OpenAPI 3.0 specification
- **WebSocket Events**: Real-time data streams for live updates
- **Webhook Support**: Get notified of events in your application
- **Rate Limiting**: Fair usage policies with generous limits
- **SDKs**: Official client libraries for Go, TypeScript, and Python
- **Sandbox Environment**: Test your integration risk-free

---

## 🔌 API Access

### Request Access

Baney Brew offers a powerful API for developers, data scientists, and businesses looking to integrate craft beer data into their applications.

**API Features:**
- 🔍 Search and filter 50,000+ beers
- 📊 Access ratings, reviews, and popularity metrics
- 🏭 Retrieve brewery information and verification status
- 🎯 Get personalized recommendations via our algorithm
- 📈 Historical data and trending analytics

**To request API access:**

1. **Sign up** for a Baney Brew account at [baneybrew.com](https://baneybrew.com)
2. **Navigate** to [baneybrew.com/api/request](https://baneybrew.com/api/request)
3. **Complete** the API access form with your use case
4. **Receive** your API key within 24 hours

### API Documentation

Our comprehensive API documentation includes:

- **Interactive Playground**: Test endpoints directly in your browser
- **Code Examples**: Sample requests in multiple languages
- **Authentication Guide**: JWT and API key authentication flows
- **Rate Limits**: Understand your usage quotas
- **Webhooks**: Set up real-time event notifications

👉 **[View API Documentation](https://developers.baneybrew.com/docs)**

### Quick Start Example

```bash
# Get beer details
curl -X GET "https://api.baneybrew.com/v1/beers/123" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json"

# Search beers by style
curl -X GET "https://api.baneybrew.com/v1/beers?style=IPA&limit=10" \
  -H "Authorization: Bearer YOUR_API_KEY"

# Get personalized recommendations
curl -X POST "https://api.baneybrew.com/v1/recommendations" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"user_id": "abc123", "limit": 20}'
```

### API Pricing

| Tier | Price | Requests/Month | Features |
|------|-------|----------------|----------|
| **Free** | $0 | 1,000 | Basic endpoints, community support |
| **Developer** | $29/mo | 50,000 | All endpoints, email support |
| **Business** | $199/mo | 500,000 | Priority support, webhooks, SLA |
| **Enterprise** | Custom | Unlimited | Dedicated support, custom integrations |

---

## 🛠️ Technology Deep Dive

### Go API Layer

Our Go-based REST API handles:
- User authentication and authorization (JWT)
- CRUD operations for breweries, beers, and ratings
- Real-time WebSocket connections for messaging
- Stripe payment processing and webhooks
- Email notifications via SMTP
- Image uploads to Azure Blob Storage

**Key Libraries:**
- `chi` - Fast, lightweight HTTP router
- `sqlx` - Direct SQL queries without ORM overhead
- `oapi-codegen` - OpenAPI 3.0 code generation
- `gorilla/websocket` - WebSocket implementation

### TypeScript Frontend

Built with Next.js 14 and the App Router:
- Server Components for improved performance
- Client-side interactivity with React 18
- Type-safe API client auto-generated from OpenAPI spec
- Real-time features with WebSocket hooks
- Responsive design with TailwindCSS
- Form validation with Zod

### Rust Compute Layer

High-performance algorithms written in Rust:

- **Recommendation Engine**: Hybrid content-based + collaborative filtering
  - KD-tree nearest neighbor search in flavor space
  - Cosine similarity for user-based collaborative filtering
  - Real-time vector calculations
  
- **Popularity Scoring**: Multi-factor ranking algorithm
  - Bayesian averaging for fair new beer rankings
  - Wilson score confidence intervals
  - Recency-weighted decay for trending detection

- **Performance**: Recommendation generation in <50ms for 100k+ beers

### Azure Infrastructure

Deployed on Azure Kubernetes Service (AKS):

```
Production Cluster:
- 3 API pods (auto-scaling 3-10)
- 2 WebSocket pods (sticky sessions)
- 1 Worker pod (background jobs)
- MySQL 8.0 (Azure Database for MySQL)
- Redis 7.0 (Azure Cache for Redis)
- Blob Storage (beer images, avatars)
```

**Infrastructure as Code:**
- Kubernetes manifests in `/infra/kubernetes`
- Helm charts for complex deployments
- GitHub Actions for CI/CD
- Azure Monitor for logging and metrics

---

## 📚 Resources

- **[Technical Blog](https://engineering.baneybrew.com)** - Deep dives into our architecture
- **[API Status](https://status.baneybrew.com)** - Real-time uptime monitoring
- **[Developer Discord](https://discord.gg/kZxsKRXywK)** - Join our community
- **[GitHub Discussions](https://github.com/baneybrew/discussions)** - Ask questions

---

## 🤝 Contributing

While Baney Brew is a proprietary platform, we welcome contributions to our open-source projects:

- **[baney-brew-sdk-go](https://github.com/baneybrew/sdk-go)** - Official Go SDK
- **[baney-brew-sdk-ts](https://github.com/baneybrew/sdk-ts)** - Official TypeScript SDK
- **[flavor-chart-component](https://github.com/baneybrew/flavor-chart)** - React flavor chart visualization

Please read our [Contributing Guidelines](CONTRIBUTING.md) before submitting a PR.

---

## 📄 License

This project is proprietary software. For licensing inquiries, contact [legal@baneybrew.com](mailto:legal@baneybrew.com).

---

## 📞 Contact

- **General Inquiries**: [hello@baneybrew.com](mailto:hello@baneybrew.com)
- **API Support**: [api@baneybrew.com](mailto:api@baneybrew.com)
- **Business Development**: [partnerships@baneybrew.com](mailto:partnerships@baneybrew.com)
- **Security Issues**: [security@baneybrew.com](mailto:security@baneybrew.com)

---

<div align="center">

**Built with 🍺 by the Baney Brew Team**

[Twitter](https://twitter.com/baneybrew) • [LinkedIn](https://linkedin.com/company/baneybrew) • [Instagram](https://instagram.com/baneybrew)

</div>
