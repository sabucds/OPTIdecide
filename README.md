# 🎯 OPTIdecide

**Advanced Decision Support System for Supply Chain Optimization Under Uncertainty**

A sophisticated full-stack application that solves complex facility location and transportation optimization problems. OPTIdecide employs industrial-strength linear programming solvers and advanced decision theory to provide optimal resource allocation strategies when facing uncertain market conditions.

> 🎓 **Academic Research Project**: This system represents the practical implementation of research presented in our college thesis: ["Sistema de apoyo para la toma de decisiones en problemas de optimización bajo incertidumbre"](https://unimet.ent.sirsi.net/custom/web/tesis/13/TA168C824.pdf). The thesis explores mathematical optimization methodologies and decision support systems for solving complex resource allocation problems under uncertainty.

## ✨ Key Features

### 🧮 Industrial-Strength Optimization Engine
- **External LP Solver Integration**: Built-in lp_solve 5.5 with custom JavaScript wrapper
- **Multi-Model Generation**: P-Model for primary optimization, Q-Model for alternative solutions
- **Three Uncertainty Methods**: Comprehensive approaches for handling uncertain parameters
- **Binary & Integer Programming**: Support for facility selection and resource allocation decisions

### 🎲 Advanced Decision-Making Under Uncertainty
- **Robustness Criteria**: Performance evaluation across uncertain scenarios with configurable robustness index
- **Laplace Criteria**: Equal probability weighting for uncertainty scenarios
- **Savage Criteria (Minimax Regret)**: Minimizes maximum regret across all possible scenarios
- **Decision Matrix Analysis**: Comprehensive payoff matrices for scenario evaluation

### 🚚 Supply Chain & Logistics Optimization
- **Facility Location Selection**: Optimal placement of distribution centers and warehouses
- **Transportation Cost Minimization**: Efficient routing from factories through distribution centers to clients
- **Capacity Planning**: Balances demand against facility and transportation constraints
- **Multi-Product Support**: Handles complex product flows across the supply chain
- **Budget Constraints**: Finds optimal solutions within financial limitations

### 📊 Comprehensive Analytics & Visualization
- **Interactive Solution Graphs**: Visual representation of factory-location-client relationships using React Digraph
- **Multiple Solution Views**: Compare final solutions, alternative solutions, and initial problem data
- **Excel Integration**: Template-based bulk data entry with automatic processing
- **Mathematical Model Export**: Generates models in Lingo format for verification
- **Performance Metrics**: Execution time tracking and solution quality analysis

## 🏗️ Architecture

### Frontend Application
- **Client App** (Port 3001): Modern Next.js interface for problem configuration and solution visualization

### Backend Services
- **GraphQL API** (Port 3000): Apollo Server with comprehensive mathematical modeling capabilities
- **Mathematical Engine**: Custom LP solving with uncertainty modeling and constraint generation
- **File Processing**: Excel template processing with data validation and transformation

### Advanced Mathematical Components
- **P-Model Constructor**: Generates primary optimization models with deterministic and uncertain constraints
- **Q-Model Generator**: Creates alternative solution models using W-constraint methodology
- **Uncertainty Solvers**: Three distinct methods for incorporating uncertain parameters
- **Decision Criteria Engine**: Multi-criteria analysis for solution selection under uncertainty

## 🚀 Getting Started

### Prerequisites
- Node.js >= 16.0.0
- npm >= 8.0.0

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/sabucds/OPTIdecide.git
cd OPTIdecide
```

2. **Install dependencies**
```bash
npm install
```

3. **Start development servers**
```bash
npm run dev
```

Applications will be available at:
- **Client App**: http://localhost:3001
- **GraphQL API**: http://localhost:3000/graphql

### Production Deployment
```bash
npm run build
docker-compose up -d
```

## 🎯 Use Cases & Applications

### Supply Chain Optimization
- **Distribution Network Design**: Determine optimal locations for warehouses and distribution centers
- **Transportation Cost Reduction**: Minimize shipping costs while meeting all demand constraints
- **Capacity Planning**: Balance facility capacities against market demand requirements
- **Multi-Echelon Inventory**: Optimize product flows from factories through distribution centers to customers

### Decision-Making Under Uncertainty
- **Market Demand Variability**: Handle uncertain customer demand with robust optimization
- **Cost Fluctuations**: Account for variable transportation and operational costs
- **Scenario Planning**: Evaluate solutions across multiple future market scenarios
- **Risk Management**: Select robust solutions that perform well under various conditions

## 🔬 Mathematical Models & Methods

### Core Optimization Models
- **P-Model**: Primary linear programming formulation with deterministic constraints
- **Q-Model**: Alternative solution generation using epsilon-constraint methodology
- **W-Constraint Method**: Iterative approach for generating diverse solution sets

### Decision Variables
- **x_client_location**: Binary assignment of clients to distribution locations
- **y_location**: Binary selection of distribution center locations
- **z_product_factory_location**: Integer product flows from factories to locations

### Constraint Types
- **Assignment Constraints**: Each client assigned to exactly one location
- **Selection Constraints**: Clients only assigned to selected locations
- **Capacity Constraints**: Demand does not exceed location/factory capacity
- **Budget Constraints**: Total location selection costs within budget limits
- **Flow Constraints**: Product balance across the supply chain network

### Uncertainty Handling Methods
1. **Method 1**: Full uncertainty modeling with 4 constraints per uncertain variable
2. **Method 2**: Simplified approach with 2 constraints per uncertain variable
3. **Method 3**: Iterative W-constraint method for robust solution generation

## 💻 Technical Stack

### Frontend Technologies
- **Next.js 13.2.4** with React 18.2.0 and TypeScript 5.0.2
- **Apollo Client 3.7.10** for GraphQL integration
- **TailwindCSS 3.3.0** for responsive styling
- **React Hook Form 7.47.0** for form management
- **React Digraph 9.1.2** for solution visualization
- **@tanstack/react-table 8.10.7** for data tables

### Backend Technologies
- **Apollo Server 4.5.0** with GraphQL schema
- **Express.js 4.18.2** framework
- **Mongoose 7.0.3** for database operations
- **External LP Solver**: lp_solve 5.5 with JavaScript wrapper
- **AWS S3 Integration** for file storage

### Infrastructure & DevOps
- **Docker** containerization with multi-service orchestration
- **Traefik** reverse proxy with SSL termination
- **Turborepo** for monorepo build optimization
- **Sentry** for error monitoring and performance tracking

## 📁 Project Structure

```
OPTIdecide/
├── apps/
│   ├── client/              # User-facing Next.js application (Port 3001)
│   └── api/                 # GraphQL API server (Port 3000)
│       ├── src/components/
│       │   ├── mathModel/   # Core mathematical modeling
│       │   ├── user/        # User management
│       │   └── s3/          # File storage integration
│       └── utils/modelFunctions/
│           ├── decisionCriteria.ts    # Multi-criteria decision analysis
│           ├── solve.ts               # Main optimization solver
│           ├── generatePModel.ts      # Primary model generation
│           ├── generateQModel.ts      # Alternative model generation
│           └── lpSolve/               # External solver integration
├── packages/
│   ├── ui/                  # Shared React components
│   └── eslint-config-custom/  # Shared linting configuration
├── docker-compose.yml       # Container orchestration
└── turbo.json              # Monorepo build configuration
```

## 🔧 Key APIs & Integrations

### GraphQL Operations
- **Model Management**: Create, update, and query optimization models
- **Solution Generation**: Execute mathematical optimization with uncertainty handling
- **Results Analysis**: Retrieve and analyze multiple solutions with decision criteria
- **File Processing**: Upload and process Excel templates for bulk data entry

### Excel Template Integration
- **Structured Data Entry**: Predefined templates for complex optimization problems
- **Automatic Validation**: Data consistency checks and relationship validation
- **Bulk Processing**: Efficient handling of large-scale optimization problems

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) and [Code of Conduct](CODE_OF_CONDUCT.md).

## 📄 License

This project is licensed under the terms specified in the [LICENSE](LICENSE) file.

---

**🚀 Optimizing supply chains and logistics with mathematical precision and uncertainty-aware decision-making**