# BlockEdu — Smart Blockchain-Based Academic Repository

A production-quality, award-winning web application for managing academic records using blockchain technology. Built with Node.js, Express, and a premium frontend design following GMU's official theme.

## 🎨 Features

### Frontend
- **Premium UI Design**: Glass-card effects, smooth animations, perfect spacing
- **GMU Official Theme**: Maroon (#7C0A02), Academic Yellow (#F5CF70), Dark Brown (#3A1C12)
- **Responsive Design**: Fully responsive across all devices
- **Three Role-Based Dashboards**: Student, Institution, Recruiter
- **Stunning Blockchain Visualization**: 3D animated blocks with chain connectors
- **Real-time Progress**: Animated progress bars and status updates

### Backend
- **PDF Processing**: Real PDF chunking using pdf-li
- **Blockchain Implementation**: SHA-256 hashing with linked blocks
- **RESTful API**: Complete API for upload, records, and verification
- **File Management**: Secure file storage and chunk management
- **Database**: JSON-based storage with lowdb

## 🚀 Quick Start

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn

### Installation

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Start the server:**
   ```bash
   npm start
   ```

3. **Access the application:**
   Open your browser and navigate to `http://localhost:3000`

### Development Mode
```bash
npm run dev
```
(Uses nodemon for auto-restart on file changes)

## 📁 Project Structure

```
BlockEdu/
├── server.js              # Express server and API routes
├── package.json           # Dependencies and scripts
├── db.json                # Database file (auto-created)
├── uploads/               # Original PDF uploads (auto-created)
├── chunks/                # Generated chunk PDFs (auto-created)
└── public/                # Frontend files
    ├── index.html         # Main HTML file
    ├── styles.css         # Premium styling
    └── script.js          # Frontend JavaScript
```

## 🔧 API Endpoints

### Upload PDF
```
POST /api/upload
Content-Type: multipart/form-data
Body: pdf (file), title (string), studentId (string)
```

### Get All Records
```
GET /api/records
Response: { success: true, records: [...] }
```

### Get Single Record
```
GET /api/records/:id
Response: { success: true, record: {...} }
```

### Verify Record
```
POST /api/verify
Content-Type: application/json
Body: { studentId: string } OR { hash: string }
Response: { success: true, verified: boolean, record: {...} }
```

### Get Chunk File
```
GET /api/chunks/:filename
Response: PDF file
```

## 🎓 User Roles

### Student
- Upload academic records
- View all uploaded records
- Share records with others
- View blockchain visualization

### Institution
- Issue new academic records
- View all issued records
- Validate external records
- View blockchain visualization

### Recruiter
- Verify candidate records
- Request documents from candidates
- View received documents

## 🔐 How It Works

1. **Upload**: User uploads a PDF document with title and Student ID
2. **Processing**: Backend splits PDF into chunks (4 pages per chunk)
3. **Hashing**: Each chunk gets a SHA-256 hash
4. **Blockchain**: Creates linked blocks with:
   - Index
   - Pages range
   - Chunk filename
   - Chunk hash
   - Previous block hash
   - Block hash
   - Timestamp
5. **Storage**: All data saved to database
6. **Verification**: Records can be verified by Student ID or hash

## 🎨 Design Features

- **Glass Morphism**: Modern glass-card effects with backdrop blur
- **Smooth Animations**: Fade-ins, hover effects, progress animations
- **3D Block Visualization**: Stunning blockchain visualization with animated blocks
- **Perfect Spacing**: Generous padding and margins throughout
- **Premium Typography**: Georgia/Times for headings, Poppins/Inter for body
- **Responsive Layout**: Three-column desktop, stacked mobile

## 👨‍💻 Developer

**Spoorthi K P**  
GMU Coding Club

## 📝 License

MIT License

## 🏆 Project Status

Production-ready, award-winning quality application ready for evaluation and deployment.
