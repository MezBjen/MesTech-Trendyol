# 🤖 eKural - AI Yönetim ve Geliştirme Sistemi

**Dosya ID:** MESTECH-EKURAL-MASTER-2025-07-02  
**Son Güncelleme:** 2025-07-02 17:59:00 (Test Sync System)  
**Amaç:** Yapay Zeka destekli otomatik geliştirme kuralları ve prosedürleri  
**Hedef:** Temiz, organize, verimli yazılım geliştirme süreci  

---

## 📋 AI İlk Tanışma ve Okuma Protokolü

### **🔍 ADIM 1: Proje Tarama ve Analiz**

Her AI etkileşiminde önce şu dosyalar okunmalı:

```bash
📁 Temel Okuma Listesi (Öncelik Sırasıyla):
1. /MesTech/Docs/eKural/kural.md (BU DOSYA - Ana Kurallar)
2. /MesTech/Docs/WINDOWS_DESKTOP_DASHBOARD_MIMARISI_VE_YOLHARITASI.md
3. /MesTech_Trendyol/Docs/birlesenler/BIRLESENLER_ROTGENI_VE_YOL_HARITASI.md  
4. /MesTech_Trendyol/Docs/birlesenler/DOSYA_HARITASI_VE_BILESEN_ANALIZI.md
5. /MesTech_Trendyol/PROJECT_STATUS_DASHBOARD.md
6. /MesTech/Docs/ altındaki tüm rapor dosyaları
```

### **🎯 ADIM 2: Aktif Proje Durumu Belirleme**

AI'ın her çalışma başında kontrol etmesi gerekenler:

- [ ] Hangi fazda olduğumuzu belirle (FAZ 1-4)
- [ ] Son commit'leri kontrol et
- [ ] Aktif branch'i belirle (main/development)
- [ ] Çalışmayan/eksik bileşenleri tespit et
- [ ] Güncel teknoloji stack'ini doğrula (.NET 9, WPF, Node.js versiyonları)

---

## 🗂️ Dosya Organizasyon Sistemi

### **📁 Ana Klasör Yapısı (MASTER)**

```
MesTech/ (ANA KÖKLER)
├── 📁 Docs/ (Tüm dokümantasyon burada)
│   ├── eKural/ (AI kuralları ve prosedürler)
│   ├── Raporlar/ (Analiz raporları)
│   └── Mimari/ (Teknik dokümantasyon)
├── 📁 MesTech_Desktop_Hub/ (YENİ - Birleşik dashboard)
│   ├── Core/ (Temel servisler)
│   ├── Modules/ (Dashboard modülleri)
│   ├── Views/ (UI katmanı)
│   └── Services/ (Backend servisler)
├── 📁 MesTech_Trendyol/ (Mevcut - Refactor edilecek)
├── 📁 MesTech_Stok/ (Mevcut - Entegre edilecek)
├── 📁 Archive/ (Kullanılmayan/eski dosyalar)
└── 📁 Backup/ (Yedek dosyalar)
```

### **🧹 Temizlik ve Organizasyon Kuralları**

#### **SİLİNECEK/ARŞİVLENECEK:**
- [ ] Duplikasyon dosyalar (temp_, backup_, _old uzantılı)
- [ ] Çalışmayan Node.js sunucu dosyaları
- [ ] Kullanılmayan test dosyaları
- [ ] Boş klasörler
- [ ] Eski versiyon dosyaları

#### **KORUNACAK/ENTEGRE EDİLECEK:**
- [ ] Çalışan .NET desktop uygulamaları
- [ ] API entegrasyon kodları
- [ ] Veritabanı schema dosyaları
- [ ] Konfigürasyon dosyaları
- [ ] Dokümantasyon ve raporlar

---

## ⚙️ Geliştirme Prosedürleri

### **💻 Kod Geliştirme Kuralları**

#### **1. Yeni Kod Yazma Protokolü:**
```csharp
// AI Kod Yazma Standardı:
// 1. Namespace: MesTech.[ModuleName]
// 2. Dependency Injection kullan
// 3. Async/await pattern uygula
// 4. Logging ekle (Serilog)
// 5. Error handling implement et
// 6. Unit test yazılabilir yap

namespace MesTech.Desktop.Hub.Core
{
    public interface IExampleService
    {
        Task<Result<T>> DoSomethingAsync<T>(string input);
    }
}
```

#### **2. Dosya Adlandırma Konvensiyonu:**
- **Servisler:** `*Service.cs` (örn: `AuthenticationService.cs`)
- **View Models:** `*ViewModel.cs` (örn: `DashboardViewModel.cs`)
- **Interfaces:** `I*Service.cs` (örn: `IApiService.cs`)
- **Models:** `*Model.cs` (örn: `UserModel.cs`)
- **Views:** `*View.xaml` (örn: `LoginView.xaml`)

### **🔧 Build ve Deployment**

#### **Build Hedefleri:**
```bash
# Debug Build (Geliştirme):
dotnet build --configuration Debug

# Release Build (Production):
dotnet build --configuration Release --output ./publish

# Test Çalıştırma:
dotnet test --logger "console;verbosity=detailed"
```

#### **Deployment Lokasyonları:**
- **Development:** `/bin/Debug/net9.0-windows/`
- **Staging:** `/publish/staging/`
- **Production:** `/publish/production/`
- **Backup:** `/backup/deployments/[timestamp]/`

---

## 📦 Yedekleme Sistemi

### **🔄 Otomatik Yedekleme Kuralları**

#### **Günlük Yedekleme (Her commit öncesi):**
```powershell
# AI'ın çalıştırması gereken yedekleme scripti:
$timestamp = Get-Date -Format "yyyyMMdd_HHmmss"
$backupPath = "backup/daily/$timestamp"

# Kaynak kod yedekleme
xcopy "src/" "$backupPath/src/" /E /H /C /I

# Veritabanı yedekleme  
xcopy "data/" "$backupPath/data/" /E /H /C /I

# Konfigürasyon yedekleme
xcopy "*.config" "$backupPath/config/" /H /C /I
```

#### **Haftalık Tam Yedekleme:**
- [ ] Tüm projeli klasörleri
- [ ] Git repository export
- [ ] Dependency packages
- [ ] Documentation ve raporlar

### **🗃️ Yedek Dosya Yönetimi**

#### **Retention Policy:**
- **Günlük yedekler:** 7 gün sakla
- **Haftalık yedekler:** 4 hafta sakla  
- **Aylık yedekler:** 6 ay sakla
- **Milestone yedekleri:** Süresiz sakla

---

## 🔀 GitHub Yönetimi ve Repository Stratejisi

### **🏢 Repository Organizasyon Yapısı**

#### **Önerilen GitHub Yapısı:**
```
🏢 GitHub Organization: MesTechSync
├── � meschain-sync-enterprise (ANA REPOSITORY)
│   ├── MesTech_Trendyol/
│   ├── MesTech_Stok/
│   ├── MesTech_Opencart/
│   └── README.md (Ana proje açıklaması)
│
└── 📁 MesTech-Desktop-Hub (YENİ MODÜLER DESKTOP PROJESI)
    ├── MesTech.Desktop.Hub/
    ├── MesTech.Shared/
    ├── MesTech.Trendyol/
    ├── MesTech.Stok/
    ├── MesTech.Dropshipping/
    ├── MesTech.Backup/
    ├── MesTech.Monitoring/
    ├── MesTech.Pazaryerleri/
    ├── Published/
    ├── Docs/
    └── README.md (Desktop hub projesi)
```

#### **🎯 Repository Stratejisi:**

**Seçenek 1: Ayrı Repository (ÖNERİLEN)**
```
https://github.com/MesTechSync/MesTech-Desktop-Hub
```

**Avantajları:**
- ✅ Tamamen temiz başlangıç
- ✅ Modüler yapıya uygun
- ✅ Bağımsız versiyonlama
- ✅ Farklı takım erişim yetkileri
- ✅ Ayrı release cycle'ları

**Seçenek 2: Alt Klasör**
```
https://github.com/MesTechSync/meschain-sync-enterprise/tree/main/MesTech-Desktop-Hub
```

**Dezavantajları:**
- ❌ Karışık commit history
- ❌ Büyük repository boyutu
- ❌ Versiyonlama karmaşası

### **� Repository Kurulum Stratejileri**

#### **STRATEJİ A: Yeni Temiz Repository (ÖNERİLEN)**

**Avantajları:**
- ✅ Tamamen temiz commit history
- ✅ Modüler yapıya uygun branch yapısı  
- ✅ Bağımsız versiyonlama ve tagging
- ✅ Farklı takım access kontrolü
- ✅ Ayrı CI/CD pipeline'ları

```bash
# GitHub'da yeni repository oluştur
# Repository Name: MesTech-Desktop-Hub
# Description: Modular Windows Desktop Hub for MesTech Marketplace Management
# Visibility: Private (ilk aşamada)

# Local'de clone et
git clone https://github.com/MesTechSync/MesTech-Desktop-Hub.git
cd MesTech-Desktop-Hub
```

#### **STRATEJİ B: Fork + Clean Branch Yaklaşımı**

**Ne zaman kullanılır:**
- 🔄 Mevcut repository'den bazı dosyaları taşımak istiyorsanız
- 📋 Commit history'den belirli modüllerin geçmişini korumak istiyorsanız
- 🔗 Ana repository ile bağlantıyı sürdürmek istiyorsanız

```bash
# 1. Ana repository'yi fork et
# GitHub UI'da "Fork" butonuna tıkla
# https://github.com/MesTechSync/meschain-sync-enterprise -> Fork

# 2. Fork'u clone et
git clone https://github.com/[YourUsername]/meschain-sync-enterprise.git
cd meschain-sync-enterprise

# 3. Desktop modülü için özel branch oluştur
git checkout -b feature/desktop-hub-migration
git checkout --orphan desktop-hub-clean

# 4. Sadece gerekli dosyaları tut
git rm -rf MesTech_*
git rm -rf *.md
git clean -fd

# 5. Yeni modüler yapıyı ekle
mkdir -p MesTech.Desktop.Hub MesTech.Shared
# ... dosyaları ekle

# 6. Clean commit
git add .
git commit -m "�🚀 Desktop Hub: Clean modular structure"
```

#### **STRATEJİ C: Selective Migration (Hibrit)**

**Kullanım Senaryosu:**
- 📦 Belirli modüllerin kodlarını yeni repository'ye taşımak
- 📚 Dokümantasyon ve konfigürasyonları korumak
- 🔄 Gelişmiş git operations kullanmak

```bash
# 1. Yeni repository oluştur (Strateji A)
git clone https://github.com/MesTechSync/MesTech-Desktop-Hub.git
cd MesTech-Desktop-Hub

# 2. Ana repository'yi remote olarak ekle
git remote add source https://github.com/MesTechSync/meschain-sync-enterprise.git
git fetch source

# 3. Belirli dosyaları seçerek çek
git checkout source/main -- MesTech_Trendyol/
git checkout source/main -- MesTech_Stok/

# 4. Dosyaları yeni yapıya taşı
mkdir -p MesTech.Trendyol/src
mv MesTech_Trendyol/* MesTech.Trendyol/src/
rmdir MesTech_Trendyol

# 5. Modüler yapıya uygun commit
git add .
git commit -m "🔄 Migration: Trendyol module to modular structure"
```

### **🚀 Repository Kurulum Prosedürü (Strateji A)**

#### **Adım 1: Yeni Repository Oluşturma**
```bash
# GitHub'da yeni repository oluştur
# Repository Name: MesTech-Desktop-Hub
# Description: Modular Windows Desktop Hub for MesTech Marketplace Management
# Visibility: Private (ilk aşamada)

# Local'de clone et
git clone https://github.com/MesTechSync/MesTech-Desktop-Hub.git
cd MesTech-Desktop-Hub
```

#### **Adım 2: İlk Commit Yapısı**
```bash
# Klasör yapısını oluştur
mkdir -p {MesTech.Desktop.Hub,MesTech.Shared,MesTech.Trendyol,MesTech.Stok}
mkdir -p {MesTech.Dropshipping,MesTech.Backup,MesTech.Monitoring,MesTech.Pazaryerleri}
mkdir -p {Published,Docs,Tests,Scripts}

# .gitignore oluştur
echo "bin/
obj/
*.user
*.suo
.vs/
Published/
*.log" > .gitignore

# İlk commit
git add .
git commit -m "🎉 Initial commit: MesTech Desktop Hub project structure

- Created modular project structure
- Added all module directories
- Setup gitignore for .NET projects
- Ready for modular development

Project Type: Modular Windows Desktop Application
Technology Stack: .NET 9, WPF, SQLite
Architecture: Hub + Independent Modules"

git push origin main
```

#### **Adım 3: Branch Stratejisi**
```bash
# Development branch oluştur
git checkout -b development
git push origin development

# Module-specific branch'ler
git checkout -b feature/trendyol-module
git checkout -b feature/stok-module
git checkout -b feature/hub-ui

# Integration branch
git checkout -b integration/all-modules

# Branch protection rules (GitHub UI'da):
# - main: Require PR, 1 reviewer, dismiss stale reviews
# - development: Require PR, no reviewer required
# - feature/*: Direct push allowed for development
```

### **🔄 Fork-Based Development Workflow**

#### **Fork Repository Kurulum (Takım Çalışması)**

```bash
# 1. Ana repository'yi fork et (GitHub UI)
# https://github.com/MesTechSync/MesTech-Desktop-Hub -> Fork

# 2. Fork'u clone et
git clone https://github.com/[DevUsername]/MesTech-Desktop-Hub.git
cd MesTech-Desktop-Hub

# 3. Upstream remote ekle
git remote add upstream https://github.com/MesTechSync/MesTech-Desktop-Hub.git
git remote -v
# origin    https://github.com/[DevUsername]/MesTech-Desktop-Hub.git (fetch)
# origin    https://github.com/[DevUsername]/MesTech-Desktop-Hub.git (push) 
# upstream  https://github.com/MesTechSync/MesTech-Desktop-Hub.git (fetch)
# upstream  https://github.com/MesTechSync/MesTech-Desktop-Hub.git (push)
```

#### **Fork Sync İşlemleri**

```bash
# Upstream'den değişiklikleri çek
git fetch upstream
git checkout main
git merge upstream/main

# Fork'u güncel tut
git push origin main

# Development branch'i de sync et
git checkout development
git merge upstream/development
git push origin development
```

#### **Feature Branch Workflow (Fork'ta)**

```bash
# 1. Feature branch oluştur
git checkout development
git pull upstream development
git checkout -b feature/[module-name]-[feature-description]

# Örnek:
git checkout -b feature/trendyol-order-sync

# 2. Development yap
# ... kod değişiklikleri

# 3. Commit yap
git add .
git commit -m "✨ Trendyol: Add order synchronization feature

- Implemented real-time order fetching
- Added order status mapping
- Created local database schema
- Added error handling and retry logic

Closes: #123
Breaking: No
Testing: Unit tests added"

# 4. Fork'a push et
git push origin feature/trendyol-order-sync

# 5. Pull Request oluştur (GitHub UI)
# From: [DevUsername]/MesTech-Desktop-Hub:feature/trendyol-order-sync
# To: MesTechSync/MesTech-Desktop-Hub:development
```

### **🔀 Migration Scripts ve Otomatik Kurulum**

#### **Hızlı Kurulum Script'i (setup-desktop-hub.ps1)**

```powershell
# setup-desktop-hub.ps1
param(
    [Parameter(Mandatory=$true)]
    [ValidateSet("new", "fork", "migration")]
    [string]$Strategy,
    
    [string]$GitHubUsername = "",
    [string]$SourceRepoUrl = "https://github.com/MesTechSync/meschain-sync-enterprise.git"
)

Write-Host "🚀 MesTech Desktop Hub Setup - Strategy: $Strategy" -ForegroundColor Green

switch ($Strategy) {
    "new" {
        Write-Host "📁 Creating new clean repository setup..."
        git clone https://github.com/MesTechSync/MesTech-Desktop-Hub.git
        cd MesTech-Desktop-Hub
        
        # Create modular structure
        $modules = @(
            "MesTech.Desktop.Hub", "MesTech.Shared", "MesTech.Trendyol", 
            "MesTech.Stok", "MesTech.Dropshipping", "MesTech.Backup",
            "MesTech.Monitoring", "MesTech.Pazaryerleri"
        )
        
        foreach ($module in $modules) {
            New-Item -ItemType Directory -Path $module -Force
            New-Item -ItemType File -Path "$module\.gitkeep" -Force
        }
        
        # Create supporting directories
        New-Item -ItemType Directory -Path "Published", "Docs", "Tests", "Scripts" -Force
        
        Write-Host "✅ Clean repository structure created" -ForegroundColor Green
    }
    
    "fork" {
        if (-not $GitHubUsername) {
            $GitHubUsername = Read-Host "Enter your GitHub username"
        }
        
        Write-Host "🔄 Setting up fork-based development..."
        git clone "https://github.com/$GitHubUsername/MesTech-Desktop-Hub.git"
        cd MesTech-Desktop-Hub
        
        # Add upstream
        git remote add upstream https://github.com/MesTechSync/MesTech-Desktop-Hub.git
        git fetch upstream
        
        Write-Host "✅ Fork setup complete with upstream remote" -ForegroundColor Green
    }
    
    "migration" {
        Write-Host "📦 Setting up selective migration from existing repository..."
        
        # Clone new repo
        git clone https://github.com/MesTechSync/MesTech-Desktop-Hub.git
        cd MesTech-Desktop-Hub
        
        # Add source as remote
        git remote add source $SourceRepoUrl
        git fetch source
        
        Write-Host "✅ Migration setup ready. Use selective checkout for specific files." -ForegroundColor Green
        Write-Host "Example: git checkout source/main -- MesTech_Trendyol/" -ForegroundColor Yellow
    }
}

Write-Host "🎯 Next steps:" -ForegroundColor Cyan
Write-Host "  1. Create your feature branch: git checkout -b feature/[module-name]" -ForegroundColor Gray
Write-Host "  2. Start development in your assigned module" -ForegroundColor Gray
Write-Host "  3. Follow commit conventions in Docs/eKural/kural.md" -ForegroundColor Gray
```

#### **Selective Migration Helper Script**

```bash
#!/bin/bash
# migrate-module.sh

MODULE_NAME=$1
SOURCE_PATH=$2
TARGET_PATH=$3

if [ -z "$MODULE_NAME" ] || [ -z "$SOURCE_PATH" ] || [ -z "$TARGET_PATH" ]; then
    echo "Usage: ./migrate-module.sh <module-name> <source-path> <target-path>"
    echo "Example: ./migrate-module.sh Trendyol MesTech_Trendyol MesTech.Trendyol"
    exit 1
fi

echo "🔄 Migrating $MODULE_NAME module..."

# Ensure we're in the desktop hub repo
if [ ! -d ".git" ]; then
    echo "❌ Error: Not in a git repository"
    exit 1
fi

# Check if source remote exists
if ! git remote get-url source > /dev/null 2>&1; then
    echo "Adding source remote..."
    git remote add source https://github.com/MesTechSync/meschain-sync-enterprise.git
    git fetch source
fi

# Create target directory
mkdir -p "$TARGET_PATH/src"
mkdir -p "$TARGET_PATH/docs"
mkdir -p "$TARGET_PATH/tests"

# Selective checkout
echo "📦 Checking out files from source..."
git checkout source/main -- "$SOURCE_PATH/"

# Move to modular structure
if [ -d "$SOURCE_PATH" ]; then
    echo "📁 Restructuring to modular format..."
    
    # Move source code
    find "$SOURCE_PATH" -name "*.cs" -o -name "*.csproj" -o -name "*.sln" | xargs -I {} cp {} "$TARGET_PATH/src/"
    
    # Move documentation
    find "$SOURCE_PATH" -name "*.md" -o -name "*.txt" | xargs -I {} cp {} "$TARGET_PATH/docs/"
    
    # Move tests
    find "$SOURCE_PATH" -path "*/test*" -o -path "*/Test*" | xargs -I {} cp {} "$TARGET_PATH/tests/"
    
    # Clean up original
    rm -rf "$SOURCE_PATH"
    
    echo "✅ Module $MODULE_NAME migrated to $TARGET_PATH"
else
    echo "❌ Source path $SOURCE_PATH not found"
    exit 1
fi

# Create module-specific gitignore
cat > "$TARGET_PATH/.gitignore" << EOF
bin/
obj/
*.user
*.suo
.vs/
*.log
appsettings.local.json
EOF

# Stage changes
git add "$TARGET_PATH"
git status

echo "🎯 Ready to commit! Use:"
echo "git commit -m \"🔄 Migration: $MODULE_NAME module to modular structure\""
```

### **👥 Team Collaboration & Access Management**

#### **Repository Access Levels**

```markdown
## 🏢 MesTech-Desktop-Hub Access Matrix

### **Repository Permissions:**
- **Admin:** Team Lead, DevOps Engineer
- **Maintain:** Senior Developers, Module Owners  
- **Write:** Active Developers
- **Triage:** QA Engineers, Technical Writers
- **Read:** Stakeholders, Part-time Contributors

### **Branch Protection Settings:**

**main branch:**
- ✅ Require pull request reviews: 2 reviewers
- ✅ Dismiss stale reviews when new commits pushed
- ✅ Require review from code owners
- ✅ Require status checks to pass before merging
- ✅ Require conversation resolution before merging
- ✅ Include administrators

**development branch:**
- ✅ Require pull request reviews: 1 reviewer
- ✅ Require status checks to pass before merging
- ❌ Include administrators (faster development)

**feature/* branches:**
- ❌ No protection (allow direct push for development)
```

#### **Team Fork Management**

```bash
# Team Leader: Repository ownership transfer
# GitHub UI: Settings -> General -> Transfer ownership

# Team Member: Fork için standart workflow
git clone https://github.com/[Username]/MesTech-Desktop-Hub.git
cd MesTech-Desktop-Hub
git remote add upstream https://github.com/MesTechSync/MesTech-Desktop-Hub.git

# Daily sync routine
git fetch upstream
git checkout development
git merge upstream/development
git push origin development
```

#### **Module Ownership Assignment**

```yaml
# .github/CODEOWNERS
# Global owners
* @team-lead @devops-engineer

# Module-specific owners
MesTech.Trendyol/ @trendyol-team @senior-dev-1
MesTech.Stok/ @stok-team @senior-dev-2
MesTech.Dropshipping/ @dropshipping-team @senior-dev-3
MesTech.Backup/ @backup-team @senior-dev-4
MesTech.Monitoring/ @monitoring-team @senior-dev-5
MesTech.Pazaryerleri/ @marketplace-team @senior-dev-6

# Infrastructure
Published/ @devops-engineer @team-lead
Scripts/ @devops-engineer
Docs/ @tech-writer @team-lead
Tests/ @qa-team @senior-dev-1

# Shared components (require multiple approvals)
MesTech.Shared/ @team-lead @senior-dev-1 @senior-dev-2
MesTech.Desktop.Hub/ @team-lead @ui-ux-dev @senior-dev-1
```

#### **Pull Request Templates**

```markdown
<!-- .github/pull_request_template.md -->
## 🔄 Pull Request: [Module Name] - [Feature/Fix Description]

### **📋 Change Summary**
- [ ] New feature
- [ ] Bug fix  
- [ ] Performance improvement
- [ ] Documentation update
- [ ] Breaking change

### **🎯 Module(s) Affected**
- [ ] MesTech.Trendyol
- [ ] MesTech.Stok
- [ ] MesTech.Dropshipping
- [ ] MesTech.Backup
- [ ] MesTech.Monitoring
- [ ] MesTech.Pazaryerleri
- [ ] MesTech.Shared
- [ ] MesTech.Desktop.Hub

### **✅ Testing Checklist**
- [ ] Unit tests added/updated
- [ ] Integration tests pass
- [ ] Manual testing completed
- [ ] Published directory build successful
- [ ] No breaking changes to other modules

### **📖 Documentation**
- [ ] Code comments updated
- [ ] README.md updated (if needed)
- [ ] API documentation updated
- [ ] CHANGELOG.md entry added

### **🔗 Related Issues**
Closes #[issue-number]
Related to #[issue-number]

### **📸 Screenshots (if UI changes)**
[Add screenshots here]

### **🚨 Breaking Changes**
[Describe any breaking changes]

---
**Reviewer Assignment:**
- **Module Owner:** @[module-owner]
- **Technical Review:** @[tech-reviewer]  
- **Final Approval:** @[team-lead]
```

#### **Issue Templates**

```yaml
# .github/ISSUE_TEMPLATE/bug_report.yml
name: 🐛 Bug Report
description: Create a bug report for MesTech Desktop Hub
title: "[BUG] [Module]: Brief description"
labels: ["bug", "needs-triage"]
body:
  - type: dropdown
    id: module
    attributes:
      label: Affected Module
      options:
        - MesTech.Trendyol
        - MesTech.Stok
        - MesTech.Dropshipping
        - MesTech.Backup
        - MesTech.Monitoring
        - MesTech.Pazaryerleri
        - MesTech.Desktop.Hub
        - MesTech.Shared
        - Published/Integration
        - Other
    validations:
      required: true
      
  - type: textarea
    id: description
    attributes:
      label: Bug Description
      description: Clear description of the bug
    validations:
      required: true
      
  - type: textarea
    id: reproduction
    attributes:
      label: Steps to Reproduce
      description: Step-by-step instructions
      placeholder: |
        1. Open module...
        2. Click on...
        3. See error...
    validations:
      required: true
      
  - type: textarea
    id: expected
    attributes:
      label: Expected Behavior
    validations:
      required: true
      
  - type: textarea
    id: environment
    attributes:
      label: Environment
      description: OS, .NET version, Visual Studio version
    validations:
      required: true
```

```yaml
# .github/ISSUE_TEMPLATE/feature_request.yml  
name: ✨ Feature Request
description: Suggest a new feature for MesTech Desktop Hub
title: "[FEATURE] [Module]: Brief description"
labels: ["enhancement", "needs-discussion"]
body:
  - type: dropdown
    id: module
    attributes:
      label: Target Module
      options:
        - MesTech.Trendyol
        - MesTech.Stok
        - MesTech.Dropshipping
        - MesTech.Backup
        - MesTech.Monitoring
        - MesTech.Pazaryerleri
        - MesTech.Desktop.Hub
        - MesTech.Shared
        - New Module
    validations:
      required: true
      
  - type: textarea
    id: problem
    attributes:
      label: Problem Statement
      description: What problem does this feature solve?
    validations:
      required: true
      
  - type: textarea
    id: solution
    attributes:
      label: Proposed Solution
      description: Describe your ideal solution
    validations:
      required: true
      
  - type: textarea
    id: alternatives
    attributes:
      label: Alternative Solutions
      description: Any alternative solutions considered?
      
  - type: dropdown
    id: priority
    attributes:
      label: Priority Level
      options:
        - Low
        - Medium
        - High
        - Critical
    validations:
      required: true
```

### **🚀 GitHub Actions & CI/CD Automation (GÜNCEL)**

**📁 Dosya Konumları (Bu workspace'de):**
```
MesTech/
├── .github/workflows/sync-ekural-to-all-repos.yml ← ANA WORKFLOW
├── Scripts/sync-status-dashboard.ps1 ← STATUS DASHBOARD  
├── Scripts/sync-ekural-manual.ps1 ← MANUEL SYNC
├── Scripts/setup-github-actions.ps1 ← SETUP TOOL
└── .github/README-SYNC-SYSTEM.md ← SISTEM DOKÜMANI
```

**🔗 GitHub Hedefleri:**
```
https://github.com/MesTechSync/meschain-sync-enterprise ← MASTER REPO
https://github.com/MesTechSync/MesTech-Desktop-Hub ← SYNC TARGET 1
https://github.com/MesTechSync/MesTech-Trendyol-Software ← SYNC TARGET 2
... (ve diğer 8 repository)
```

#### **Modular Build Workflow**

```yaml
# .github/workflows/build-modules.yml
name: 🔨 Build All Modules

on:
  push:
    branches: [ main, development ]
  pull_request:
    branches: [ main, development ]

env:
  DOTNET_VERSION: '9.0'

jobs:
  detect-changes:
    runs-on: ubuntu-latest
    outputs:
      modules: ${{ steps.changes.outputs.modules }}
    steps:
      - uses: actions/checkout@v4
      - uses: dorny/paths-filter@v2
        id: changes
        with:
          filters: |
            trendyol:
              - 'MesTech.Trendyol/**'
            stok:
              - 'MesTech.Stok/**'
            dropshipping:
              - 'MesTech.Dropshipping/**'
            backup:
              - 'MesTech.Backup/**'
            monitoring:
              - 'MesTech.Monitoring/**'
            pazaryerleri:
              - 'MesTech.Pazaryerleri/**'
            shared:
              - 'MesTech.Shared/**'
            hub:
              - 'MesTech.Desktop.Hub/**'

  build-modules:
    runs-on: windows-latest
    needs: detect-changes
    strategy:
      matrix:
        module: [trendyol, stok, dropshipping, backup, monitoring, pazaryerleri, shared, hub]
    steps:
      - uses: actions/checkout@v4
      
      - name: Setup .NET
        uses: actions/setup-dotnet@v4
        with:
          dotnet-version: ${{ env.DOTNET_VERSION }}
          
      - name: Check if module changed
        id: check
        run: |
          if [[ "${{ needs.detect-changes.outputs.modules }}" == *"${{ matrix.module }}"* ]]; then
            echo "changed=true" >> $GITHUB_OUTPUT
          else
            echo "changed=false" >> $GITHUB_OUTPUT
          fi
        shell: bash
        
      - name: Restore dependencies
        if: steps.check.outputs.changed == 'true'
        run: dotnet restore MesTech.${{ matrix.module }}/
        
      - name: Build
        if: steps.check.outputs.changed == 'true'
        run: dotnet build MesTech.${{ matrix.module }}/ --no-restore --configuration Release
        
      - name: Test
        if: steps.check.outputs.changed == 'true'
        run: dotnet test MesTech.${{ matrix.module }}/ --no-build --configuration Release --verbosity normal

  integration-build:
    runs-on: windows-latest
    needs: build-modules
    if: github.ref == 'refs/heads/main' || github.ref == 'refs/heads/development'
    steps:
      - uses: actions/checkout@v4
      
      - name: Setup .NET
        uses: actions/setup-dotnet@v4
        with:
          dotnet-version: ${{ env.DOTNET_VERSION }}
          
      - name: Build Published Integration
        run: |
          ./Scripts/build-all-modules.ps1
          ./Scripts/publish-integration.ps1
        shell: pwsh
        
      - name: Upload Published Artifacts
        uses: actions/upload-artifact@v4
        with:
          name: published-integration-${{ github.sha }}
          path: Published/
          retention-days: 30
```

#### **Release Automation**

```yaml
# .github/workflows/release.yml
name: 🚀 Release MesTech Desktop Hub

on:
  push:
    tags:
      - 'v*.*.*'

jobs:
  release:
    runs-on: windows-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0
          
      - name: Setup .NET
        uses: actions/setup-dotnet@v4
        with:
          dotnet-version: '9.0'
          
      - name: Build Release
        run: |
          ./Scripts/build-all-modules.ps1 -Configuration Release
          ./Scripts/publish-release.ps1 -Version ${{ github.ref_name }}
        shell: pwsh
        
      - name: Generate Release Notes
        id: release_notes
        run: |
          ./Scripts/generate-release-notes.ps1 -Tag ${{ github.ref_name }}
        shell: pwsh
        
      - name: Create Release
        uses: actions/create-release@v1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          tag_name: ${{ github.ref_name }}
          release_name: MesTech Desktop Hub ${{ github.ref_name }}
          body_path: ./release-notes.md
          draft: false
          prerelease: false
          
      - name: Upload Release Assets
        uses: actions/upload-release-asset@v1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          upload_url: ${{ steps.create_release.outputs.upload_url }}
          asset_path: ./Published/MesTech-Desktop-Hub-${{ github.ref_name }}.zip
          asset_name: MesTech-Desktop-Hub-${{ github.ref_name }}.zip
          asset_content_type: application/zip
```

#### **Automated Code Quality**

```yaml
# .github/workflows/code-quality.yml
name: 🔍 Code Quality & Security

on:
  push:
    branches: [ main, development ]
  pull_request:
    branches: [ main, development ]

jobs:
  analyze:
    runs-on: windows-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0
          
      - name: Setup .NET
        uses: actions/setup-dotnet@v4
        with:
          dotnet-version: '9.0'
          
      - name: SonarCloud Scan
        uses: SonarSource/sonarcloud-github-action@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}
          
      - name: Run CodeQL Analysis
        uses: github/codeql-action/analyze@v2
        with:
          languages: csharp
          
      - name: Security Scan
        run: |
          dotnet tool install --global security-scan
          security-scan --path . --format sarif --output security-results.sarif
        continue-on-error: true
        
      - name: Upload Security Results
        uses: github/codeql-action/upload-sarif@v2
        with:
          sarif_file: security-results.sarif
```

#### **Dependency Updates**

```yaml
# .github/workflows/dependency-updates.yml
name: 🔄 Dependency Updates

on:
  schedule:
    - cron: '0 2 * * 1' # Her Pazartesi saat 02:00
  workflow_dispatch:

jobs:
  update-dependencies:
    runs-on: windows-latest
    steps:
      - uses: actions/checkout@v4
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          
      - name: Setup .NET
        uses: actions/setup-dotnet@v4
        with:
          dotnet-version: '9.0'
          
      - name: Update NuGet packages
        run: |
          $modules = Get-ChildItem -Directory -Name "MesTech.*"
          foreach ($module in $modules) {
            Write-Host "Updating $module..."
            dotnet list $module package --outdated
            dotnet add $module package --update
          }
        shell: pwsh
        
      - name: Create Pull Request
        uses: peter-evans/create-pull-request@v5
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          commit-message: "🔄 chore: Update NuGet packages"
          title: "🔄 Automated NuGet Package Updates"
          body: |
            ## 📦 Automated Dependency Updates
            
            This PR contains automated updates for NuGet packages across all modules.
            
            ### 🔍 Changes Made:
            - Updated outdated NuGet packages
            - Maintained compatibility across modules
            
            ### ✅ Testing Required:
            - [ ] All modules build successfully  
            - [ ] Integration tests pass
            - [ ] No breaking changes introduced
            
            **Auto-generated by GitHub Actions**
          branch: automated/dependency-updates
          delete-branch: true
```

#### **Issue & PR Automation**

```yaml
# .github/workflows/issue-automation.yml
name: 🎯 Issue & PR Automation

on:
  issues:
    types: [opened, labeled]
  pull_request:
    types: [opened, labeled, ready_for_review]

jobs:
  auto-assign:
    runs-on: ubuntu-latest
    if: github.event.action == 'opened'
    steps:
      - name: Auto-assign based on labels
        uses: actions/github-script@v7
        with:
          script: |
            const { owner, repo } = context.repo;
            const issue = context.payload.issue || context.payload.pull_request;
            
            // Module-based assignment
            const moduleAssignments = {
              'module:trendyol': ['trendyol-team'],
              'module:stok': ['stok-team'],
              'module:dropshipping': ['dropshipping-team'],
              'module:backup': ['backup-team'],
              'module:monitoring': ['monitoring-team'],
              'module:pazaryerleri': ['marketplace-team'],
              'module:shared': ['team-lead', 'senior-dev-1'],
              'module:hub': ['ui-ux-dev', 'team-lead']
            };
            
            for (const label of issue.labels) {
              if (moduleAssignments[label.name]) {
                await github.rest.issues.addAssignees({
                  owner,
                  repo,
                  issue_number: issue.number,
                  assignees: moduleAssignments[label.name]
                });
                break;
              }
            }
            
            // Priority-based labeling
            if (issue.title.includes('[URGENT]') || issue.title.includes('[CRITICAL]')) {
              await github.rest.issues.addLabels({
                owner,
                repo,
                issue_number: issue.number,
                labels: ['priority:high', 'needs-immediate-attention']
              });
            }

  stale-issues:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/stale@v9
        with:
          repo-token: ${{ secrets.GITHUB_TOKEN }}
          stale-issue-message: |
            🕐 This issue has been automatically marked as stale because it has not had recent activity.
            
            **Next Steps:**
            - Add comment to keep it open
            - Close if no longer relevant
            - Move to backlog if lower priority
            
            It will be closed if no further activity occurs. Thank you for your contributions.
          stale-pr-message: |
            🕐 This pull request has been automatically marked as stale because it has not had recent activity.
            
            **Required Actions:**
            - Rebase with latest development branch
            - Address review comments
            - Request re-review if ready
            
            It will be closed if no further activity occurs.
          stale-issue-label: 'stale'
          stale-pr-label: 'stale'
          days-before-stale: 30
          days-before-close: 7
```

---

## 🎯 Fazlı Geliştirme Kuralları

### **📊 Faz Takibi**

#### **Aktif Faz Kontrolü:**
AI her session başında kontrol etmeli:

```markdown
## FAZ DURUM RAPORU
**Aktif Faz:** [FAZ 1/2/3/4]
**Tamamlanma Oranı:** [%XX]
**Kalan Görevler:** [XX adet]
**Kritik Blocker'lar:** [Var/Yok]
**Sonraki Milestone:** [Tarih]
```

#### **Faz Geçiş Kriterleri:**

**FAZ 1 → FAZ 2:**
- [ ] Authentication service %100 çalışıyor
- [ ] Ana dashboard layout hazır
- [ ] Navigation sistemi aktif
- [ ] İlk modül (Trendyol) test edildi

**FAZ 2 → FAZ 3:**
- [ ] Core modüller entegre edildi
- [ ] API gateway stabilize oldu
- [ ] Temel UI/UX tamamlandı

**FAZ 3 → FAZ 4:**
- [ ] Tüm modüller çalışır vaziyette
- [ ] Performance testleri geçti
- [ ] Security audit tamamlandı

---

## 🚀 AI Çalışma Talimatları

### **🔍 Her Session'da Yapılacaklar:**

1. **📖 Dokuman Okuma (5 dakika):**
   - Bu kural dosyasını oku
   - Proje durumu raporlarını kontrol et
   - Son değişiklikleri gözden geçir

2. **🎯 Görev Belirleme (3 dakika):**
   - Aktif faz ve öncelikleri belirle
   - Takım görevlerini kontrol et
   - Kritik blocker'ları tespit et

3. **💻 Kod Geliştirme (Ana süre):**
   - Belirlenen görevleri gerçekleştir
   - Kod standartlarına uy
   - Test yazımını ihmal etme

4. **📦 Yedekleme ve Commit (3 dakika):**
   - Değişiklikleri yedekle
   - Git commit'i standardına uy
   - Dokümantasyonu güncelle

### **⚠️ AI İçin YASAK Eylemler:**

- [ ] ❌ Ana dosyaları silme (onay almadan)
- [ ] ❌ Çalışan kodu bozma  
- [ ] ❌ Backup almadan major değişiklik
- [ ] ❌ Test olmadan commit atma
- [ ] ❌ Dokümantasyon güncellemeden kod yazma

### **✅ AI İçin ZORUNLU Eylemler:**

- [ ] ✅ Her değişiklik öncesi backup
- [ ] ✅ Her commit'te test çalıştırma
- [ ] ✅ Error handling ekleme
- [ ] ✅ Logging implementasyonu
- [ ] ✅ Code review için açıklama yazma

---

## 📈 Kalite Kontrol Sistemi

### **🔍 Pre-Commit Checklist:**

```markdown
## AI ÖN KONTROL LİSTESİ ✅

### Kod Kalitesi:
- [ ] Syntax hataları yok
- [ ] Naming conventions uygulandı
- [ ] Error handling mevcut
- [ ] Async patterns kullanıldı
- [ ] Dependency injection implementli

### Test Durumu:
- [ ] Unit testler yazıldı
- [ ] Tüm testler geçiyor
- [ ] Code coverage >80%
- [ ] Integration testler çalışıyor

### Dokümantasyon:
- [ ] Method summary'leri eklendi
- [ ] README güncellendi
- [ ] API dokümantasyonu hazır
- [ ] Kullanım örnekleri mevcut

### Security:
- [ ] SQL injection koruması
- [ ] Input validation var
- [ ] Authentication kontrolleri
- [ ] Sensitive data şifrelendi
```

### **📊 Performance Metrikleri:**

AI'ın takip etmesi gereken KPI'lar:
- **Build Time:** <30 saniye
- **Test Execution:** <60 saniye  
- **App Startup:** <5 saniye
- **Memory Usage:** <500MB
- **CPU Usage:** <%25 (idle durumda)

---

## 🔧 Sorun Giderme Protokolü

### **🚨 Build Hataları:**

```powershell
# AI'ın çalıştıracağı hata giderme scripti:

# 1. Clean solution
dotnet clean

# 2. Restore packages  
dotnet restore

# 3. Rebuild
dotnet build --verbosity diagnostic

# 4. Log kontrolü
Get-Content "build.log" | Select-String "error"
```

### **🔧 Dependency Sorunları:**

```bash
# Package restore
dotnet restore --force

# Cache temizleme
dotnet nuget locals all --clear

# Specific package update
dotnet add package [PackageName] --version [Version]
```

### **🐛 Runtime Hataları:**

1. **Log dosyalarını kontrol et:** `/logs/[date]/`
2. **Exception details'i yakala:** Stack trace + Inner exceptions
3. **Performance counters'ı oku:** Memory, CPU, Thread count
4. **Database connectivity'yi test et:** Connection strings
5. **External API'ları doğrula:** Network connectivity + API keys

---

## 📞 Acil Durum Prosedürleri

### **🔴 CRITICAL FAILURE Response:**

```markdown
## ACIL DURUM PROTOKOLÜ 🚨

### Immediate Actions (0-5 dakika):
1. 🛑 STOP all development
2. 📋 Document exact error details  
3. 📦 Create emergency backup
4. 🔄 Rollback to last working version
5. 📧 Notify stakeholders

### Investigation Phase (5-30 dakika):
1. 🔍 Root cause analysis
2. 📊 Impact assessment  
3. 🛠️ Quick fix vs proper solution
4. ⏱️ Time estimation for fix
5. 📋 Communication plan

### Recovery Phase (30+ dakika):
1. 🔧 Implement fix
2. 🧪 Test thoroughly
3. 📦 Deploy with monitoring
4. 📊 Performance validation
5. 📝 Post-mortem documentation
```

---

## 🎓 Eğitim ve Gelişim

### **📚 AI Sürekli Öğrenme:**

AI'ın güncel kalması için kaynaklar:
- **.NET 9 Updates:** Microsoft docs
- **WPF Best Practices:** Community guidelines  
- **Security Patches:** CVE databases
- **Performance Optimization:** Profiling tools
- **Industry Trends:** Technology blogs

### **🏆 Milestone Ödülleri:**

Her fazın tamamlanmasında:
- [ ] 📊 Performance benchmark raporu
- [ ] 🎯 Achievement badge creation
- [ ] 📈 Progress visualization
- [ ] 🔄 Process improvement notes
- [ ] 🎉 Team recognition post

---

## 📄 Son Notlar

**Bu kural dosyası dinamiktir ve sürekli güncellenmelidir.**

### **📝 Güncelleme Prosedürü:**
1. Yeni ihtiyaçlar tespit edildikçe ekle
2. Çalışmayan kuralları çıkar
3. Best practice'leri integrate et
4. Team feedback'ini incorporate et
5. Version control uygula

### **📊 Başarı Metrikleri:**
- **Code Quality Score:** Sürekli artış
- **Bug Count:** Sürekli azalış  
- **Development Speed:** Sürekli optimizasyon
- **Team Satisfaction:** Yüksek moral
- **Customer Satisfaction:** Kullanıcı memnuniyeti

---

**🤖 AI Message:** "Bu kuralları okudum, anladım ve uygulayacağım. MesTech projesini en verimli şekilde geliştirmek için bu prosedürleri takip edeceğim."

**📅 Son Güncelleme:** 2025-07-02  
**👤 Güncelleyen:** GitHub Copilot AI  
**📋 Versiyon:** v1.0.0  
**🎯 Hedef:** Mükemmel yazılım geliştirme süreci

---

## 🔄 Repository Migration Stratejisi

#### **Mevcut Kodları Yeni Repository'ye Taşıma:**
```powershell
# Migration Script (migrate-to-new-repo.ps1)
Write-Host "🚀 MesTech Desktop Hub Migration Başlatılıyor..."

# 1. Yeni repository'yi clone et
if (!(Test-Path "MesTech-Desktop-Hub")) {
    git clone https://github.com/MesTechSync/MesTech-Desktop-Hub.git
}

cd MesTech-Desktop-Hub

# 2. Mevcut kodları selektif olarak kopyala
$sourceRoot = "../meschain-sync-enterprise/MesTech"

# Shared kütüphane için ortak kodları al
Copy-Item "$sourceRoot/MesTech_Trendyol/src/MesTechTrendyol.Core/*" `
    "MesTech.Shared/" -Recurse -Force

# Trendyol modülü için kodları al  
Copy-Item "$sourceRoot/MesTech_Trendyol/src/MesTechTrendyol.Desktop/*" `
    "MesTech.Trendyol/" -Recurse -Force

# Stok modülü için kodları al
Copy-Item "$sourceRoot/MesTech_Stok/MesTechStok/*" `
    "MesTech.Stok/" -Recurse -Force

# Dokümantasyonu kopyala
Copy-Item "$sourceRoot/Docs/*" "Docs/" -Recurse -Force

Write-Host "✅ Migration tamamlandı!"
Write-Host "🔍 Dosyaları gözden geçirin ve gereksizleri temizleyin"
```

#### **🧹 Temizlik ve Yeniden Yapılandırma:**
```bash
# Gereksiz dosyaları temizle
Remove-Item -Recurse -Force @(
    "**/*temp*",
    "**/*backup*", 
    "**/*old*",
    "**/bin",
    "**/obj",
    "**/*.user"
)

# .csproj dosyalarını yeniden düzenle
foreach ($module in @("Shared", "Trendyol", "Stok", "Desktop.Hub")) {
    $projectFile = "MesTech.$module/MesTech.$module.csproj"
    # Project reference'larını güncelle
    # Package reference'larını temizle
    # Output path'leri Published klasörüne yönlendir
}
```

### **📋 Repository Yönetim Kuralları**

#### **Branch Protection Rules:**
```yaml
main:
  - Require pull request reviews: true
  - Dismiss stale reviews: true
  - Require status checks to pass: true
  - Require branches to be up to date: true
  - Include administrators: true

development:
  - Require pull request reviews: false
  - Allow force pushes: true
  - Allow deletions: false
```

#### **Commit Message Convention (Yeni Repo için):**
```
🎯 [MODULE] - Brief description

Detailed changes:
- ✅ Added: New functionality
- 🔧 Modified: Existing feature  
- 🗑️ Removed: Deprecated code
- 🐛 Fixed: Bug resolution
- 📝 Docs: Documentation update

Module: MesTech.[ModuleName]
Phase: FAZ [1-4]
Test Status: [PASSED/FAILED/PENDING]
Files Changed: [X] files
```

#### **Release Management:**
```
v1.0.0-alpha    - FAZ 1 Complete (Hub + Shared)
v1.1.0-alpha    - FAZ 2 Complete (+ 3 Modules) 
v1.2.0-beta     - FAZ 3 Complete (+ All Modules)
v1.3.0-rc       - FAZ 4 Complete (Production Ready)
v1.3.0          - Final Release
```

### **🔒 Repository Security ve Access Management**

#### **Team Access Levels:**
```yaml
Admins:
  - Full access to all repositories
  - Can create/delete repositories
  - Can modify protection rules

Backend Team (MezBjen):
  - Write access to: MesTech.Shared, MesTech.Desktop.Hub
  - Read access to: All modules

Frontend Team (Cursor):  
  - Write access to: MesTech.Desktop.Hub, UI modules
  - Read access to: All modules

Module Teams:
  - Write access to: Their specific module
  - Read access to: MesTech.Shared, other modules

DevOps Team (Musti):
  - Write access to: Scripts, Published, Docs
  - Admin access to: CI/CD, Releases
```

#### **🚨 Emergency Procedures:**
```bash
# Acil durumda repository rollback
git revert [commit-hash] --no-edit
git push origin main

# Branch koruma
git branch --set-upstream-to=origin/main main
git config branch.main.mergeoptions --no-ff

# Backup repository
git clone --mirror https://github.com/MesTechSync/MesTech-Desktop-Hub.git
```

---

## 🏢 **ENTERPRISE HİBRİT KARMA STRATEJİSİ**

### **🎯 MesChain-Sync-Enterprise → Modüler Yazılım Ekosistemi**

#### **Mevcut Durum Analizi:**
```
📦 meschain-sync-enterprise (Ana Depo - LEGACY)
├── MesTech_Trendyol/ (Çalışan yazılım)
├── MesTech_Stok/ (Çalışan yazılım) 
├── MesTech_Opencart/ (Çalışan yazılım)
├── MesTech_Amazon_tr/ (Çalışan yazılım)
├── MesTech_Hepsiburada/ (Çalışan yazılım)
├── MesTech_N11/ (Çalışan yazılım)
├── MesTech_Pazarama/ (Çalışan yazılım)
├── MesTech_Ozon/ (Çalışan yazılım)
├── MesTech_PttAVM/ (Çalışan yazılım)
├── MesTech_Dashboard/ (Birleştirici panel)
├── MesTech_Security/ (Güvenlik katmanı)
├── MesTech_AI/ (Yapay zeka servisleri)
└── [Çok fazla karışık dosya - temizlenecek]
```

#### **Hedef Enterprise Ekosistem:**
```
🏢 GitHub Organization: MesTechSync

📂 CORE INFRASTRUCTURE:
├── 🔧 MesTech-Core-Infrastructure (Private)
│   ├── Authentication/ (SSO, OAuth2, JWT)
│   ├── Database/ (Shared schemas, migrations) 
│   ├── API-Gateway/ (Microservices router)
│   ├── Logging/ (Centralized logging)
│   ├── Monitoring/ (Health checks, metrics)
│   └── Security/ (Encryption, certificates)

📂 MARKETPLACE YAZILIMLARI (Her biri ayrı software):
├── 🛒 MesTech-Trendyol-Software (Public/Private Hybrid)
├── 📦 MesTech-Stok-Management (Public/Private Hybrid)
├── 🌐 MesTech-Opencart-Integration (Public/Private Hybrid)
├── 📋 MesTech-Amazon-Turkey (Private)
├── 🏪 MesTech-Hepsiburada-Sync (Private)
├── 🔗 MesTech-N11-Connector (Private)
├── 💳 MesTech-Pazarama-Bridge (Private)
├── 🌍 MesTech-Ozon-International (Private)
├── 📮 MesTech-PttAVM-Gateway (Private)

📂 PLATFORM SERVICES:
├── 🎛️ MesTech-Desktop-Hub (Private) - Ana birleştirici panel
├── 🛡️ MesTech-Security-Suite (Private) - Güvenlik merkezi
├── 🤖 MesTech-AI-Engine (Private) - Yapay zeka servisleri
├── 📊 MesTech-Analytics-Platform (Private) - Raporlama
└── 🔄 MesTech-Backup-System (Private) - Yedekleme sistemi
```

### **🔗 Repository URL Yapısı ve Linkler**

#### **Ana Organization:**
```
🏢 https://github.com/MesTechSync/
```

#### **Core Infrastructure (Private Repositories):**
```bash
# Temel altyapı servisleri
https://github.com/MesTechSync/MesTech-Core-Infrastructure
https://github.com/MesTechSync/MesTech-API-Gateway  
https://github.com/MesTechSync/MesTech-Authentication-Service
https://github.com/MesTechSync/MesTech-Database-Schemas
```

#### **Marketplace Yazılımları (Hibrit Lisanslama):**
```bash
# E-ticaret platform entegrasyonları
https://github.com/MesTechSync/MesTech-Trendyol-Software      # 🔓 Public Core + 🔐 Private Premium
https://github.com/MesTechSync/MesTech-Stok-Management        # 🔓 Public Core + 🔐 Private Enterprise  
https://github.com/MesTechSync/MesTech-Opencart-Integration   # 🔓 Public Core + 🔐 Private Modules
https://github.com/MesTechSync/MesTech-Amazon-Turkey          # 🔐 Private (API keys gerekli)
https://github.com/MesTechSync/MesTech-Hepsiburada-Sync       # 🔐 Private (Commercial license)
https://github.com/MesTechSync/MesTech-N11-Connector          # 🔐 Private (Business license)
https://github.com/MesTechSync/MesTech-Pazarama-Bridge        # 🔐 Private (Enterprise license)
https://github.com/MesTechSync/MesTech-Ozon-International     # 🔐 Private (International license)
https://github.com/MesTechSync/MesTech-PttAVM-Gateway         # 🔐 Private (Government contract)
```

#### **Platform & Hub (Private):**
```bash
# Ana platform ve yönetim araçları
https://github.com/MesTechSync/MesTech-Desktop-Hub            # 🔐 Private - Ana birleştirici panel
https://github.com/MesTechSync/MesTech-Security-Suite         # 🔐 Private - Güvenlik merkezi
https://github.com/MesTechSync/MesTech-AI-Engine              # 🔐 Private - Yapay zeka servisleri
https://github.com/MesTechSync/MesTech-Analytics-Platform     # 🔐 Private - Raporlama platformu
https://github.com/MesTechSync/MesTech-Backup-System          # 🔐 Private - Yedekleme sistemi
```

### **🔐 Hibrit Lisanslama Stratejisi**

#### **Lisans Yapısı:**
```yaml
Repository Types:
  Public-Core:
    License: "MIT License"
    Description: "Temel işlevsellik, topluluk kullanımı"
    Features:
      - Basic API integration
      - Simple UI components  
      - Documentation
      - Community support
    
  Private-Premium:
    License: "Commercial License"
    Description: "Gelişmiş özellikler, ticari kullanım"
    Features:
      - Advanced automation
      - Premium UI/UX
      - Priority support
      - Custom integrations
      
  Private-Enterprise:
    License: "Enterprise License"  
    Description: "Kurumsal çözümler, tam destek"
    Features:
      - White-label solutions
      - Custom development
      - SLA guarantees
      - On-premise deployment
      - 24/7 support
```

#### **Örnek Hibrit Yapı - Trendyol Software:**
```
📂 MesTech-Trendyol-Software/
├── 🔓 Core/ (Public - MIT License)
│   ├── Basic API calls
│   ├── Simple product sync
│   ├── Basic order management
│   └── Documentation
├── 🔐 Premium/ (Private - Commercial License)
│   ├── Advanced automation
│   ├── Bulk operations
│   ├── Advanced reporting
│   └── Custom workflows
└── 🔐 Enterprise/ (Private - Enterprise License)
    ├── White-label UI
    ├── Custom integrations
    ├── Advanced analytics
    └── Multi-tenant support
```

### **🏗️ Migration Roadmap (Karma Strateji)**

#### **Faz 1: Repository Ayrıştırma (4 hafta)**
```powershell
# Her yazılım için ayrı repository oluşturma
$yazilimlar = @(
    "Trendyol", "Stok", "Opencart", "Amazon", "Hepsiburada", 
    "N11", "Pazarama", "Ozon", "PttAVM"
)

foreach ($yazilim in $yazilimlar) {
    Write-Host "🔄 Creating repository: MesTech-$yazilim-Software"
    
    # 1. Yeni repository oluştur
    gh repo create "MesTechSync/MesTech-$yazilim-Software" --private
    
    # 2. Mevcut kodları selective migration ile taşı
    ./Scripts/migrate-software.ps1 -Software $yazilim -Target "MesTech-$yazilim-Software"
    
    # 3. Modüler yapıya dönüştür
    ./Scripts/restructure-to-modular.ps1 -Path "MesTech-$yazilim-Software"
    
    # 4. CI/CD pipeline kurulumu
    ./Scripts/setup-cicd.ps1 -Repository "MesTech-$yazilim-Software"
}
```

#### **Faz 2: Core Infrastructure (2 hafta)**
```bash
# Ortak altyapı servislerini ayır
gh repo create "MesTechSync/MesTech-Core-Infrastructure" --private
gh repo create "MesTechSync/MesTech-API-Gateway" --private
gh repo create "MesTechSync/MesTech-Authentication-Service" --private

# Shared components'leri taşı
./migrate-shared-infrastructure.sh
```

#### **Faz 3: Desktop Hub Integration (3 hafta)**
```bash
# Ana birleştirici panel
gh repo create "MesTechSync/MesTech-Desktop-Hub" --private

# Tüm yazılımları single dashboard'da birleştir
./Scripts/create-unified-dashboard.ps1
```

#### **Faz 4: Hibrit Lisanslama (2 hafta)**
```bash
# Public core'ları ayır, premium features'ları private tut
./Scripts/implement-hybrid-licensing.ps1
```

### **🔧 Automated Migration Scripts**

#### **Software Migration Script:**
```powershell
# migrate-software.ps1
param(
    [Parameter(Mandatory=$true)]
    [string]$Software,
    [Parameter(Mandatory=$true)]
    [string]$Target
)

Write-Host "🚀 Migrating $Software to $Target" -ForegroundColor Green

# 1. Create new repository
$orgName = "MesTechSync"
$repoUrl = "https://github.com/$orgName/$Target.git"

# Clone source
git clone https://github.com/MesTechSync/meschain-sync-enterprise.git temp-source
cd temp-source

# Extract specific software
$sourcePath = "MesTech_$Software"
if (Test-Path $sourcePath) {
    # Create target repository
    gh repo create "$orgName/$Target" --private --description "Enterprise $Software Software - Modular Architecture"
    
    # Clone new repo
    git clone $repoUrl "../$Target"
    cd "../$Target"
    
    # Copy files with structure
    Copy-Item "../temp-source/$sourcePath/*" -Destination "./src/" -Recurse -Force
    
    # Create modular structure
    New-Item -ItemType Directory -Path @(
        "src", "docs", "tests", "scripts", "config", 
        "Core", "Premium", "Enterprise", 
        "API", "UI", "Services", "Database"
    ) -Force
    
    # Move files to appropriate folders
    Move-Item "src/*.cs" -Destination "src/Core/" -Force -ErrorAction SilentlyContinue
    Move-Item "src/*.csproj" -Destination "src/Core/" -Force -ErrorAction SilentlyContinue
    Move-Item "src/*.md" -Destination "docs/" -Force -ErrorAction SilentlyContinue
    
    # Create README
    @"
# MesTech $Software Software

## 🎯 Enterprise Marketplace Integration Solution

### Architecture
- **Core**: Basic functionality (MIT License)
- **Premium**: Advanced features (Commercial License)  
- **Enterprise**: Full solution (Enterprise License)

### Installation
\`\`\`bash
# Core (Free)
dotnet add package MesTech.$Software.Core

# Premium (License required)
dotnet add package MesTech.$Software.Premium

# Enterprise (Contact sales)
dotnet add package MesTech.$Software.Enterprise
\`\`\`

### Links
- **Main Hub**: https://github.com/MesTechSync/MesTech-Desktop-Hub
- **Documentation**: https://mestech.docs.com/$Software
- **Support**: https://support.mestech.com/$Software
- **Lisans**: https://mestech.com/licensing
"@ | Out-File -FilePath "README.md" -Encoding UTF8
    
    # Initial commit
    git add .
    git commit -m "🎉 Initial commit: $Software Enterprise Software

- Migrated from monorepo meschain-sync-enterprise
- Created modular architecture (Core/Premium/Enterprise)
- Setup hybrid licensing structure
- Ready for independent development

Software: $Software
Architecture: Microservice
License: Hybrid (MIT Core + Commercial Premium/Enterprise)
Target: Production-ready standalone application"

    git push origin main
    
    Write-Host "✅ $Software migration completed!" -ForegroundColor Green
    Write-Host "📍 Repository: $repoUrl" -ForegroundColor Cyan
} else {
    Write-Error "❌ Source path $sourcePath not found!"
}

# Cleanup
cd ../../
Remove-Item "temp-source" -Recurse -Force
```

#### **Hub Integration Script:**
```powershell
# create-unified-dashboard.ps1

Write-Host "🎛️ Creating MesTech Desktop Hub - Unified Dashboard" -ForegroundColor Green

# Hub repository
gh repo create "MesTechSync/MesTech-Desktop-Hub" --private --description "Enterprise Desktop Hub - Unified Dashboard for All MesTech Software"

git clone "https://github.com/MesTechSync/MesTech-Desktop-Hub.git"
cd "MesTech-Desktop-Hub"

# Create hub structure
$hubStructure = @{
    "MesTech.Hub.Core" = "Ana dashboard çekirdeği"
    "MesTech.Hub.UI" = "Birleşik kullanıcı arayüzü"
    "MesTech.Hub.API" = "Mikroservislere bağlantı"
    "MesTech.Hub.Auth" = "Kimlik doğrulama"
    "MesTech.Hub.Config" = "Konfigürasyon yönetimi"
    "Modules" = "Yazılım modülleri"
    "Services" = "Mikroservis bağlantıları"
    "Plugins" = "Eklenti sistemi"
    "Published" = "Birleşik uygulama çıktısı"
    "Scripts" = "Build ve deployment scriptleri"
}

foreach ($folder in $hubStructure.Keys) {
    New-Item -ItemType Directory -Path $folder -Force
    "$($hubStructure[$folder])" | Out-File -FilePath "$folder/.description" -Encoding UTF8
}

# Hub configuration
@"
{
  "Hub": {
    "Name": "MesTech Enterprise Desktop Hub",
    "Version": "1.0.0",
    "Architecture": "Microservices + Desktop Integration",
    "Modules": [
      {
        "Name": "Trendyol",
        "Repository": "https://github.com/MesTechSync/MesTech-Trendyol-Software",
        "License": "Hybrid",
        "Status": "Active"
      },
      {
        "Name": "Stok Management", 
        "Repository": "https://github.com/MesTechSync/MesTech-Stok-Management",
        "License": "Hybrid",
        "Status": "Active"
      },
      {
        "Name": "Opencart Integration",
        "Repository": "https://github.com/MesTechSync/MesTech-Opencart-Integration", 
        "License": "Hybrid",
        "Status": "Active"
      },
      {
        "Name": "Amazon Turkey",
        "Repository": "https://github.com/MesTechSync/MesTech-Amazon-Turkey",
        "License": "Private",
        "Status": "Active"
      },
      {
        "Name": "Hepsiburada Sync",
        "Repository": "https://github.com/MesTechSync/MesTech-Hepsiburada-Sync",
        "License": "Commercial",
        "Status": "Active"
      }
    ],
    "Services": {
      "Authentication": "https://github.com/MesTechSync/MesTech-Authentication-Service",
      "API Gateway": "https://github.com/MesTechSync/MesTech-API-Gateway",
      "Database": "https://github.com/MesTechSync/MesTech-Database-Schemas"
    }
  }
}
"@ | Out-File -FilePath "hub-config.json" -Encoding UTF8

# Build script
@"
# build-hub.ps1
Write-Host "🔨 Building MesTech Desktop Hub" -ForegroundColor Green

# 1. Clone all module repositories
\$modules = Get-Content hub-config.json | ConvertFrom-Json
foreach (\$module in \$modules.Hub.Modules) {
    \$repoName = (\$module.Repository -split '/')[-1]
    if (!(Test-Path "Modules/\$repoName")) {
        git clone \$module.Repository "Modules/\$repoName"
    }
}

# 2. Build each module
foreach (\$module in \$modules.Hub.Modules) {
    \$repoName = (\$module.Repository -split '/')[-1]
    Write-Host "Building \$(\$module.Name)..." -ForegroundColor Yellow
    
    cd "Modules/\$repoName"
    dotnet build --configuration Release --output "../../Published/\$(\$module.Name)/"
    cd "../.."
}

# 3. Build hub core
Write-Host "Building Hub Core..." -ForegroundColor Yellow
dotnet build MesTech.Hub.Core --configuration Release --output "Published/Hub/"

# 4. Create unified installer
Write-Host "Creating unified installer..." -ForegroundColor Yellow
./Scripts/create-installer.ps1

Write-Host "✅ Hub build completed!" -ForegroundColor Green
Write-Host "📍 Output: Published/" -ForegroundColor Cyan
"@ | Out-File -FilePath "Scripts/build-hub.ps1" -Encoding UTF8

# README for Hub
@"
# 🎛️ MesTech Desktop Hub

## 🏢 Enterprise Marketplace Management Platform

Tüm MesTech yazılımlarını tek bir desktop uygulamasında birleştiren merkezi yönetim platformu.

### 🔗 Entegre Yazılımlar

| Yazılım | Repository | Lisans | Durum |
|---------|------------|---------|-------|
| **Trendyol** | [MesTech-Trendyol-Software](https://github.com/MesTechSync/MesTech-Trendyol-Software) | Hibrit | ✅ Aktif |
| **Stok Management** | [MesTech-Stok-Management](https://github.com/MesTechSync/MesTech-Stok-Management) | Hibrit | ✅ Aktif |
| **Opencart Integration** | [MesTech-Opencart-Integration](https://github.com/MesTechSync/MesTech-Opencart-Integration) | Hibrit | ✅ Aktif |
| **Amazon Turkey** | [MesTech-Amazon-Turkey](https://github.com/MesTechSync/MesTech-Amazon-Turkey) | Private | ✅ Aktif |
| **Hepsiburada Sync** | [MesTech-Hepsiburada-Sync](https://github.com/MesTechSync/MesTech-Hepsiburada-Sync) | Commercial | ✅ Aktif |
| **N11 Connector** | [MesTech-N11-Connector](https://github.com/MesTechSync/MesTech-N11-Connector) | Commercial | ✅ Aktif |
| **Pazarama Bridge** | [MesTech-Pazarama-Bridge](https://github.com/MesTechSync/MesTech-Pazarama-Bridge) | Commercial | ✅ Aktif |
| **Ozon International** | [MesTech-Ozon-International](https://github.com/MesTechSync/MesTech-Ozon-International) | Enterprise | ✅ Aktif |
| **PttAVM Gateway** | [MesTech-PttAVM-Gateway](https://github.com/MesTechSync/MesTech-PttAVM-Gateway) | Government | ✅ Aktif |

### 🏗️ Mimari

\`\`\`
🎛️ MesTech Desktop Hub (Ana Panel)
├── 🔐 Authentication Service
├── 🌐 API Gateway  
├── 📊 Analytics Dashboard
└── 🔌 Module Plugin System
    ├── 🛒 E-commerce Modules
    ├── 📦 Inventory Management
    ├── 🔄 Sync Services
    └── 📈 Reporting Tools
\`\`\`

### 🚀 Kurulum

\`\`\`bash
# Hub'ı indir ve kur
git clone https://github.com/MesTechSync/MesTech-Desktop-Hub.git
cd MesTech-Desktop-Hub

# Bağımlılıkları kur
./Scripts/install-dependencies.ps1

# Hub'ı derle
./Scripts/build-hub.ps1

# Çalıştır
./Published/MesTechHub.exe
\`\`\`

### 📋 Lisanslama

- **Hub Core**: MIT License (Açık kaynak)
- **Marketplace Modules**: Hibrit (Core açık + Premium kapalı)
- **Enterprise Features**: Commercial License
- **Custom Integrations**: Enterprise License

### 🔗 Bağlantılar

- **Ana Organization**: https://github.com/MesTechSync/
- **Dokümantasyon**: https://docs.mestech.com/hub
- **Destek**: https://support.mestech.com/hub
- **Lisans**: https://mestech.com/licensing

---

**🏢 MesTech Enterprise Solutions**  
*Marketplace Management Simplified*
````
## 🔄 **AKILLI GÜNCELLEME VE SENKRONİZASYON SİSTEMİ**

### **🎯 Merkezi Kontrol Yapısı**

Bu `kural.md` dosyası **MASTER CONTROL CENTER** olarak çalışır ve tüm ayrı repository'lere otomatik olarak değişiklikleri yayar.

```
🏢 MesTech Ecosystem - Akıllı Güncelleme Sistemi

📍 MASTER CONTROL (BU DOSYA):
   📁 c:\MesChain-Sync-Enterprise\MesTech\Docs\eKural\kural.md

📡 OTOMATIK YAYIN HEDEFLERI:
├── 🎛️ https://github.com/MesTechSync/MesTech-Desktop-Hub/docs/eKural/
├── 🛒 https://github.com/MesTechSync/MesTech-Trendyol-Software/docs/eKural/
├── 📦 https://github.com/MesTechSync/MesTech-Stok-Management/docs/eKural/
├── 🌐 https://github.com/MesTechSync/MesTech-Opencart-Integration/docs/eKural/
├── 📋 https://github.com/MesTechSync/MesTech-Amazon-Turkey/docs/eKural/
├── 🏪 https://github.com/MesTechSync/MesTech-Hepsiburada-Sync/docs/eKural/
├── 🔗 https://github.com/MesTechSync/MesTech-N11-Connector/docs/eKural/
├── 💳 https://github.com/MesTechSync/MesTech-Pazarama-Bridge/docs/eKural/
├── 🌍 https://github.com/MesTechSync/MesTech-Ozon-International/docs/eKural/
└── 📮 https://github.com/MesTechSync/MesTech-PttAVM-Gateway/docs/eKural/
```

### **🤖 Otomatik Güncelleme Sistemleri**

#### **YÖNETİM 1: GitHub Actions ile Otomatik Senkronizasyon**

```yaml
# .github/workflows/sync-ekural-to-all-repos.yml
name: 🔄 Sync eKural to All Repositories

on:
  push:
    paths:
      - 'MesTech/Docs/eKural/kural.md'
    branches: [ main ]
  workflow_dispatch:

jobs:
  sync-ekural:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        repository:
          - MesTech-Desktop-Hub
          - MesTech-Trendyol-Software
          - MesTech-Stok-Management
          - MesTech-Opencart-Integration
          - MesTech-Amazon-Turkey
          - MesTech-Hepsiburada-Sync
          - MesTech-N11-Connector
          - MesTech-Pazarama-Bridge
          - MesTech-Ozon-International
          - MesTech-PttAVM-Gateway
          
    steps:
      - name: Checkout Master Repository
        uses: actions/checkout@v4
        with:
          token: ${{ secrets.MESTECH_SYNC_TOKEN }}
          
      - name: Checkout Target Repository
        uses: actions/checkout@v4
        with:
          repository: MesTechSync/${{ matrix.repository }}
          token: ${{ secrets.MESTECH_SYNC_TOKEN }}
          path: target-repo
          
      - name: Sync eKural File
        run: |
          # Create docs/eKural directory if not exists
          mkdir -p target-repo/docs/eKural
          
          # Copy master kural.md
          cp MesTech/Docs/eKural/kural.md target-repo/docs/eKural/
          
          # Add repository-specific header
          cat > target-repo/docs/eKural/repo-info.md << EOF
          # 📍 Repository Specific Information
          
          **Repository:** ${{ matrix.repository }}
          **Sync Date:** $(date)
          **Master Source:** meschain-sync-enterprise/MesTech/Docs/eKural/kural.md
          **Auto-Generated:** This file is automatically synced from master repository
          
          ## 🔗 Related Links
          - **Master Repository:** https://github.com/MesTechSync/meschain-sync-enterprise
          - **This Repository:** https://github.com/MesTechSync/${{ matrix.repository }}
          - **Desktop Hub:** https://github.com/MesTechSync/MesTech-Desktop-Hub
          EOF
          
      - name: Commit Changes
        run: |
          cd target-repo
          git config user.name "MesTech AutoSync Bot"
          git config user.email "autosync@mestech.com"
          
          if [ -n "$(git status --porcelain)" ]; then
            git add docs/eKural/
            git commit -m "🔄 Auto-sync: Update eKural from master repository
            
            - Synced latest eKural rules and procedures
            - Source: meschain-sync-enterprise/MesTech/Docs/eKural/kural.md
            - Auto-generated by GitHub Actions
            - Repository: ${{ matrix.repository }}
            
            Sync-ID: $(date +%Y%m%d-%H%M%S)
            Master-Commit: ${{ github.sha }}"
            
            git push origin main
            echo "✅ eKural synced to ${{ matrix.repository }}"
          else
            echo "ℹ️ No changes needed for ${{ matrix.repository }}"
          fi
```

#### **YÖNETİM 2: PowerShell ile Manuel Senkronizasyon**

```powershell
# Scripts/sync-ekural-manual.ps1
param(
    [switch]$DryRun = $false,
    [string[]]$TargetRepos = @(),
    [switch]$Force = $false
)

Write-Host "🔄 MesTech eKural Sync Tool v2.0" -ForegroundColor Green
Write-Host "📍 Source: $(Get-Location)\MesTech\Docs\eKural\kural.md" -ForegroundColor Gray

# Tüm repository'ler
$allRepos = @(
    "MesTech-Desktop-Hub",
    "MesTech-Trendyol-Software", 
    "MesTech-Stok-Management",
    "MesTech-Opencart-Integration",
    "MesTech-Amazon-Turkey",
    "MesTech-Hepsiburada-Sync",
    "MesTech-N11-Connector",
    "MesTech-Pazarama-Bridge",
    "MesTech-Ozon-International",
    "MesTech-PttAVM-Gateway"
)

# Target repos belirleme
if ($TargetRepos.Count -eq 0) {
    $TargetRepos = $allRepos
    Write-Host "🎯 Target: Tüm repository'ler ($($allRepos.Count) adet)" -ForegroundColor Yellow
} else {
    Write-Host "🎯 Target: Seçili repository'ler ($($TargetRepos.Count) adet)" -ForegroundColor Yellow
}

# Master kural.md kontrolü
$masterKuralPath = "MesTech\Docs\eKural\kural.md"
if (!(Test-Path $masterKuralPath)) {
    Write-Error "❌ Master kural.md dosyası bulunamadı: $masterKuralPath"
    exit 1
}

$masterKuralContent = Get-Content $masterKuralPath -Raw
$masterKuralHash = (Get-FileHash $masterKuralPath).Hash
$syncTimestamp = Get-Date -Format "yyyy-MM-dd HH:mm:ss"

Write-Host "📋 Master kural.md bilgileri:" -ForegroundColor Cyan
Write-Host "   📊 Boyut: $([math]::Round((Get-Item $masterKuralPath).Length / 1KB, 2)) KB" -ForegroundColor Gray
Write-Host "   🔒 Hash: $($masterKuralHash.Substring(0,8))..." -ForegroundColor Gray
Write-Host "   📅 Tarih: $syncTimestamp" -ForegroundColor Gray

# Temporary directory oluştur
$tempDir = "temp-sync-$(Get-Date -Format 'yyyyMMdd-HHmmss')"
New-Item -ItemType Directory -Path $tempDir -Force | Out-Null

foreach ($repo in $TargetRepos) {
    Write-Host "`n🔄 İşleniyor: $repo" -ForegroundColor Green
    
    try {
        # Repository'yi clone et
        $repoPath = "$tempDir\$repo"
        Write-Host "   📥 Cloning..." -ForegroundColor Gray
        
        if ($DryRun) {
            Write-Host "   [DRY RUN] git clone https://github.com/MesTechSync/$repo.git $repoPath" -ForegroundColor DarkYellow
        } else {
            git clone "https://github.com/MesTechSync/$repo.git" $repoPath --quiet
            if ($LASTEXITCODE -ne 0) {
                Write-Warning "   ⚠️ Clone failed for $repo - skipping"
                continue
            }
        }
        
        # docs/eKural klasörünü oluştur
        $targetKuralDir = "$repoPath\docs\eKural"
        $targetKuralPath = "$targetKuralDir\kural.md"
        
        if ($DryRun) {
            Write-Host "   [DRY RUN] mkdir $targetKuralDir" -ForegroundColor DarkYellow
        } else {
            New-Item -ItemType Directory -Path $targetKuralDir -Force | Out-Null
        }
        
        # Mevcut dosya ile karşılaştır
        $needsUpdate = $true
        if ((Test-Path $targetKuralPath) -and !$Force) {
            $currentHash = (Get-FileHash $targetKuralPath).Hash
            if ($currentHash -eq $masterKuralHash) {
                Write-Host "   ✅ Already up to date (Hash match)" -ForegroundColor Green
                $needsUpdate = $false
            }
        }
        
        if ($needsUpdate) {
            # Repository-specific header oluştur
            $repoSpecificHeader = @"
<!-- 
📍 REPOSITORY SPECIFIC INFORMATION
Repository: $repo
Sync Date: $syncTimestamp
Master Source: meschain-sync-enterprise/MesTech/Docs/eKural/kural.md
Master Hash: $masterKuralHash
Auto-Generated: This file is automatically synced from master repository

🔗 Related Links:
- Master Repository: https://github.com/MesTechSync/meschain-sync-enterprise
- This Repository: https://github.com/MesTechSync/$repo
- Desktop Hub: https://github.com/MesTechSync/MesTech-Desktop-Hub
-->

"@
            
            # Repository-specific content ekle
            $repoSpecificContent = $repoSpecificHeader + $masterKuralContent
            
            if ($DryRun) {
                Write-Host "   [DRY RUN] Writing kural.md ($([math]::Round($repoSpecificContent.Length / 1KB, 2)) KB)" -ForegroundColor DarkYellow
            } else {
                # kural.md'yi kopyala
                $repoSpecificContent | Out-File -FilePath $targetKuralPath -Encoding UTF8
                Write-Host "   📝 kural.md updated ($([math]::Round((Get-Item $targetKuralPath).Length / 1KB, 2)) KB)" -ForegroundColor Green
            }
            
            # Git commit
            if ($DryRun) {
                Write-Host "   [DRY RUN] git commit and push" -ForegroundColor DarkYellow
            } else {
                cd $repoPath
                git add docs/eKural/
                $commitMessage = @"
🔄 Auto-sync: Update eKural from master repository

- Synced latest eKural rules and procedures
- Source: meschain-sync-enterprise/MesTech/Docs/eKural/kural.md
- Repository: $repo
- Sync Timestamp: $syncTimestamp
- Master Hash: $($masterKuralHash.Substring(0,12))

This is an automated update to ensure all repositories 
follow the same development rules and procedures.
"@
                
                git commit -m $commitMessage --quiet
                if ($LASTEXITCODE -eq 0) {
                    git push origin main --quiet
                    if ($LASTEXITCODE -eq 0) {
                        Write-Host "   ✅ Pushed to remote" -ForegroundColor Green
                    } else {
                        Write-Warning "   ⚠️ Push failed for $repo"
                    }
                } else {
                    Write-Host "   ℹ️ No changes to commit" -ForegroundColor Gray
                }
                cd ".."
            }
        }
        
        Write-Host "   ✅ $repo completed" -ForegroundColor Green
        
    } catch {
        Write-Error "   ❌ Error processing $repo`: $($_.Exception.Message)"
    }
}

# Cleanup
if (!$DryRun) {
    Remove-Item $tempDir -Recurse -Force
    Write-Host "`n🧹 Temporary files cleaned up" -ForegroundColor Gray
}

Write-Host "`n✅ eKural sync completed!" -ForegroundColor Green
Write-Host "📊 Processed: $($TargetRepos.Count) repositories" -ForegroundColor Cyan
Write-Host "📅 Sync Time: $syncTimestamp" -ForegroundColor Cyan

# Kullanım örnekleri
Write-Host "`n💡 Kullanım örnekleri:" -ForegroundColor Yellow
Write-Host "   # Dry run (sadece test):" -ForegroundColor Gray
Write-Host "   ./sync-ekural-manual.ps1 -DryRun" -ForegroundColor Gray
Write-Host "`n   # Sadece belirli repo'lar:" -ForegroundColor Gray
Write-Host "   ./sync-ekural-manual.ps1 -TargetRepos @('MesTech-Trendyol-Software', 'MesTech-Desktop-Hub')" -ForegroundColor Gray
Write-Host "`n   # Force update (hash kontrolü yapmadan):" -ForegroundColor Gray
Write-Host "   ./sync-ekural-manual.ps1 -Force" -ForegroundColor Gray
```

#### **YÖNETİM 3: VS Code Extension ile Gerçek Zamanlı Sync**

```json
// .vscode/settings.json (Bu workspace'de)
{
  "mesTech.autoSync": {
    "enabled": true,
    "watchFiles": [
      "MesTech/Docs/eKural/kural.md"
    ],
    "syncTargets": [
      "https://github.com/MesTechSync/MesTech-Desktop-Hub",
      "https://github.com/MesTechSync/MesTech-Trendyol-Software",
      "https://github.com/MesTechSync/MesTech-Stok-Management"
    ],
    "autoCommit": true,
    "commitMessage": "🔄 Auto-sync: eKural updated from master"
  }
}
```

### **🔔 Akıllı Bildirim Sistemi**

#### **Değişiklik Takibi:**
```powershell
# Scripts/track-ekural-changes.ps1

# kural.md değişikliklerini izle
$kuralPath = "MesTech\Docs\eKural\kural.md"
$lastHash = Get-Content ".ekural-last-hash" -ErrorAction SilentlyContinue

$currentHash = (Get-FileHash $kuralPath).Hash

if ($lastHash -ne $currentHash) {
    Write-Host "🔄 eKural değişiklik tespit edildi!" -ForegroundColor Yellow
    
    # Değişiklikleri analiz et
    $changes = git diff HEAD~1 $kuralPath
    
    # Otomatik sync tetikle
    Write-Host "🚀 Otomatik senkronizasyon başlatılıyor..." -ForegroundColor Green
    .\Scripts\sync-ekural-manual.ps1
    
    # Hash'i kaydet
    $currentHash | Out-File ".ekural-last-hash"
    
    # Teams/Slack bildirimi gönder
    $webhookUrl = $env:MESTECH_TEAMS_WEBHOOK
    if ($webhookUrl) {
        $notification = @{
            text = "🔄 eKural güncellendi ve tüm repository'lere senkronize edildi"
            sections = @(
                @{
                    activityTitle = "MesTech eKural Auto-Sync"
                    activitySubtitle = "$(Get-Date)"
                    facts = @(
                        @{ name = "Dosya"; value = $kuralPath },
                        @{ name = "Hash"; value = $currentHash.Substring(0,12) },
                        @{ name = "Sync Hedefleri"; value = "10 repository" }
                    )
                }
            )
        } | ConvertTo-Json -Depth 4
        
        Invoke-RestMethod -Uri $webhookUrl -Method Post -Body $notification -ContentType "application/json"
    }
}
```

### **📊 Sync Status Dashboard**

```powershell
# Scripts/sync-status-dashboard.ps1

Write-Host "📊 MesTech eKural Sync Status Dashboard" -ForegroundColor Green
Write-Host "=" * 60 -ForegroundColor Gray

$repos = @(
    "MesTech-Desktop-Hub", "MesTech-Trendyol-Software", 
    "MesTech-Stok-Management", "MesTech-Opencart-Integration"
)

$masterHash = (Get-FileHash "MesTech\Docs\eKural\kural.md").Hash.Substring(0,12)
Write-Host "🎯 Master Hash: $masterHash" -ForegroundColor Cyan

foreach ($repo in $repos) {
    try {
        # GitHub API ile son commit'i kontrol et
        $apiUrl = "https://api.github.com/repos/MesTechSync/$repo/contents/docs/eKural/kural.md"
        $response = Invoke-RestMethod -Uri $apiUrl -Headers @{ "Accept" = "application/vnd.github.v3+json" }
        
        $repoHash = $response.sha.Substring(0,12)
        $lastUpdate = $response.last_modified
        
        if ($repoHash -eq $masterHash) {
            Write-Host "✅ $repo - Synced" -ForegroundColor Green
        } else {
            Write-Host "⚠️ $repo - Out of sync (Hash: $repoHash)" -ForegroundColor Yellow
        }
        
    } catch {
        Write-Host "❌ $repo - Error/Not found" -ForegroundColor Red
    }
}

Write-Host "`n💡 Sync komutları:" -ForegroundColor Yellow
Write-Host "   Manual sync: .\Scripts\sync-ekural-manual.ps1" -ForegroundColor Gray
Write-Host "   Force sync: .\Scripts\sync-ekural-manual.ps1 -Force" -ForegroundColor Gray
```

### **🎯 Kullanım Senaryoları**

#### **Senaryo 1: Bu workspace'de kural.md'yi güncellediniz**
```powershell
# Otomatik olarak şunlar olur:
1. 🔍 File watcher değişikliği algılar
2. 🚀 GitHub Action tetiklenir (eğer commit'lediyseniz)
3. 📡 10 repository'ye otomatik push edilir
4. 🔔 Teams/Slack'e bildirim gönderilir
5. ✅ Tüm yazılımlar güncel kurallara sahip olur
```

#### **Senaryo 2: Manuel kontrol ve güncelleme**
```powershell
# Sync durumunu kontrol et
.\Scripts\sync-status-dashboard.ps1

# Manuel sync (test için)
.\Scripts\sync-ekural-manual.ps1 -DryRun

# Gerçek sync
.\Scripts\sync-ekural-manual.ps1

# Sadece belirli repo'ları sync et
.\Scripts\sync-ekural-manual.ps1 -TargetRepos @('MesTech-Trendyol-Software')
```

#### **Senaryo 3: Yeni repository ekleme**
```powershell
# Yeni repo'yu sync listesine ekle
$newRepo = "MesTech-NewMarketplace-Software"

# sync-ekural-manual.ps1'deki $allRepos array'ine ekle
# GitHub Action'ın matrix'ine ekle
# Otomatik sync başlayacak
```

### **✅ Sonuç: Akıllı Ecosystem**

Bu sistemle:

✅ **Bu workspace'deki kural.md = MASTER CONTROL**
✅ **Değişiklik yaptığınızda → Otomatik olarak tüm repo'lara gider**  
✅ **Her repository kendi docs/eKural/kural.md'sine sahip**
✅ **Conflict yok, senkronize sistem**
✅ **Dashboard ile durum takibi**
✅ **Manual override mümkün**

**🚀 Hemen başlayalım mı?** Hangi sync yöntemiyle başlamak istersiniz?

---
