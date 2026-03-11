import React, { useState, useRef, useEffect } from 'react';
import { Upload, Download, Copy, Check, ChevronDown, ChevronUp, MoreVertical, FileText, Table, ImageIcon } from 'lucide-react';

// Types
interface Finding {
  id: string;
  type: 'strength' | 'improvement';
  message: string;
  bbox?: { x: number; y: number; w: number; h: number };
  severity?: 'high' | 'medium' | 'low';
}

interface SectionResult {
  name: string;
  score: number;
  findings: Finding[];
  patterns?: string[];
}

interface AnalysisResult {
  sections: Record<string, SectionResult>;
  timestamp: string;
}

// UI Components
const Button = ({ children, onClick, variant = 'default', className = '', disabled = false }: any) => {
  const baseStyles = 'px-4 py-2 rounded-lg font-medium transition-all disabled:opacity-50 disabled:cursor-not-allowed';
  const variants = {
    default: 'bg-indigo-600 text-white hover:bg-indigo-700',
    outline: 'border-2 border-gray-300 hover:border-gray-400 bg-white',
    ghost: 'hover:bg-gray-100'
  };
  return (
    <button onClick={onClick} disabled={disabled} className={`${baseStyles} ${variants[variant]} ${className}`}>
      {children}
    </button>
  );
};

const Card = ({ children, className = '' }: any) => (
  <div className={`bg-white rounded-lg border border-gray-200 shadow-sm ${className}`}>{children}</div>
);

const Badge = ({ children, variant = 'default' }: any) => {
  const variants = {
    default: 'bg-gray-100 text-gray-800',
    success: 'bg-green-100 text-green-800',
    warning: 'bg-orange-100 text-orange-800',
    purple: 'bg-purple-600 text-white'
  };
  return <span className={`inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-medium ${variants[variant]}`}>{children}</span>;
};

const Progress = ({ value, className = '' }: any) => (
  <div className={`w-full bg-gray-200 rounded-full h-2 ${className}`}>
    <div className="bg-indigo-600 h-2 rounded-full transition-all" style={{ width: `${value}%` }} />
  </div>
);

const Checkbox = ({ checked, onChange, label }: any) => (
  <label className="flex items-center space-x-2 cursor-pointer">
    <input type="checkbox" checked={checked} onChange={onChange} className="w-4 h-4 text-indigo-600 rounded border-gray-300 focus:ring-indigo-500" />
    <span className="text-sm text-gray-700">{label}</span>
  </label>
);

// Analysis Engine
const analyzeDesign = (imageData: string, aspects: string[], mode: string): AnalysisResult => {
  const results: Record<string, SectionResult> = {};

  if (aspects.includes('uxStandards')) {
    results.uxStandards = {
      name: 'UX Standards',
      score: 70,
      findings: [
        { id: '1', type: 'strength', message: 'Visual design pattern follows established conventions' },
        { id: '2', type: 'strength', message: 'Layout appears logically organized' },
        { id: '3', type: 'strength', message: 'Consistent use of color coding for data representation' },
        { id: '4', type: 'improvement', message: 'User testing needed to validate navigation effectiveness', bbox: { x: 20, y: 20, w: 150, h: 40 } },
        { id: '5', type: 'improvement', message: 'Interactive behavior requires functional verification', bbox: { x: 20, y: 80, w: 150, h: 200 } },
        { id: '6', type: 'improvement', message: 'Consider enhancing visual hierarchy for better focus' }
      ],
      patterns: ['Button - Top right', 'Search Bar - Top center', 'Navigation Menu - Left sidebar']
    };
  }

  if (aspects.includes('accessibility')) {
    results.accessibility = {
      name: 'Accessibility Compliance',
      score: 75,
      findings: [
        { id: '7', type: 'strength', message: 'All interactive elements appear to be keyboard accessible with proper tab order', bbox: { x: 50, y: 150, w: 100, h: 30 } },
        { id: '8', type: 'improvement', message: 'Some text elements have insufficient color contrast ratios. Current Ratio: Text/Background - Below WCAG AA standard. Suggestion: Increase contrast to achieve minimum 4.5:1 ratio for normal text and 3:1 for large text.', severity: 'high', bbox: { x: 200, y: 100, w: 400, h: 80 } }
      ]
    };
  }

  if (aspects.includes('culturalDiversity')) {
    results.culturalDiversity = {
      name: 'Cultural Diversity',
      score: 82,
      findings: [
        { id: '9', type: 'strength', message: 'Language choices appear neutral and inclusive' },
        { id: '10', type: 'strength', message: 'Color scheme avoids culturally sensitive combinations' },
        { id: '11', type: 'improvement', message: 'Consider adding multi-language support options' }
      ]
    };
  }

  if (aspects.includes('privacySecurity')) {
    results.privacySecurity = {
      name: 'Privacy and Security',
      score: 68,
      findings: [
        { id: '12', type: 'strength', message: 'No visible personal data exposure in interface' },
        { id: '13', type: 'improvement', message: 'Add clear privacy policy link in footer' },
        { id: '14', type: 'improvement', message: 'Consider implementing data encryption indicators' }
      ]
    };
  }

  if (aspects.includes('visualConsistency')) {
    results.visualConsistency = {
      name: 'Visual Consistency',
      score: 88,
      findings: [
        { id: '15', type: 'strength', message: 'Consistent button styles throughout the interface' },
        { id: '16', type: 'strength', message: 'Typography hierarchy is well-maintained' },
        { id: '17', type: 'strength', message: 'Spacing and alignment follow a consistent grid system' }
      ]
    };
  }

  if (aspects.includes('heuristicFeedback')) {
    results.heuristicFeedback = {
      name: 'Heuristic Feedback',
      score: 72,
      findings: [
        { id: '18', type: 'strength', message: 'Clear error prevention mechanisms visible' },
        { id: '19', type: 'improvement', message: 'Add loading states for asynchronous operations' },
        { id: '20', type: 'improvement', message: 'Enhance user feedback for completed actions' }
      ]
    };
  }

  return {
    sections: results,
    timestamp: new Date().toISOString()
  };
};

// Export Functions
const exportToExcel = (results: AnalysisResult, filename: string) => {
  let csvContent = "Section,Score,Type,Finding\n";
  Object.entries(results.sections).forEach(([key, section]) => {
    section.findings.forEach(finding => {
      const row = `"${section.name}",${section.score},"${finding.type}","${finding.message}"\n`;
      csvContent += row;
    });
  });
  
  const blob = new Blob([csvContent], { type: 'text/csv' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = filename;
  a.click();
  URL.revokeObjectURL(url);
};

const exportToJSON = (results: AnalysisResult, filename: string) => {
  const blob = new Blob([JSON.stringify(results, null, 2)], { type: 'application/json' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = filename;
  a.click();
  URL.revokeObjectURL(url);
};

// Main App
export default function UXWiseAI() {
  const [uploadedImage, setUploadedImage] = useState<string | null>(null);
  const [fileName, setFileName] = useState<string>('');
  const [mode, setMode] = useState('direct');
  const [aspects, setAspects] = useState({
    uxStandards: true,
    accessibility: true,
    culturalDiversity: true,
    privacySecurity: true,
    visualConsistency: true,
    heuristicFeedback: true
  });
  const [results, setResults] = useState<AnalysisResult | null>(null);
  const [expandedSections, setExpandedSections] = useState<Record<string, boolean>>({});
  const [copiedSection, setCopiedSection] = useState<string | null>(null);
  const [showExportMenu, setShowExportMenu] = useState(false);
  const [showAnnotations, setShowAnnotations] = useState(true);
  const fileInputRef = useRef<HTMLInputElement>(null);
  const canvasRef = useRef<HTMLCanvasElement>(null);

  const handleFileUpload = (e: React.ChangeEvent<HTMLInputElement>) => {
    const file = e.target.files?.[0];
    if (file && file.type.match('image.*')) {
      setFileName(file.name);
      const reader = new FileReader();
      reader.onload = (event) => {
        setUploadedImage(event.target?.result as string);
      };
      reader.readAsDataURL(file);
    }
  };

  const handleDragOver = (e: React.DragEvent) => {
    e.preventDefault();
  };

  const handleDrop = (e: React.DragEvent) => {
    e.preventDefault();
    const file = e.dataTransfer.files[0];
    if (file && file.type.match('image.*')) {
      setFileName(file.name);
      const reader = new FileReader();
      reader.onload = (event) => {
        setUploadedImage(event.target?.result as string);
      };
      reader.readAsDataURL(file);
    }
  };

  const handleAnalyze = () => {
    if (!uploadedImage) return;
    const selectedAspects = Object.entries(aspects)
      .filter(([_, enabled]) => enabled)
      .map(([key]) => key);
    const analysisResults = analyzeDesign(uploadedImage, selectedAspects, mode);
    setResults(analysisResults);
    const initialExpanded: Record<string, boolean> = {};
    Object.keys(analysisResults.sections).forEach(key => {
      initialExpanded[key] = true;
    });
    setExpandedSections(initialExpanded);
  };

  const toggleSection = (key: string) => {
    setExpandedSections(prev => ({ ...prev, [key]: !prev[key] }));
  };

  const copySection = (sectionKey: string) => {
    if (!results) return;
    const section = results.sections[sectionKey];
    const text = `${section.name} - Score: ${section.score}/100\n\nStrengths:\n${
      section.findings.filter(f => f.type === 'strength').map(f => `• ${f.message}`).join('\n')
    }\n\nImprovements:\n${
      section.findings.filter(f => f.type === 'improvement').map(f => `• ${f.message}`).join('\n')
    }`;
    navigator.clipboard.writeText(text);
    setCopiedSection(sectionKey);
    setTimeout(() => setCopiedSection(null), 2000);
  };

  const handleReset = () => {
    setUploadedImage(null);
    setFileName('');
    setResults(null);
    setExpandedSections({});
  };

  useEffect(() => {
    if (uploadedImage && canvasRef.current && results && showAnnotations) {
      const canvas = canvasRef.current;
      const ctx = canvas.getContext('2d');
      if (!ctx) return;

      const img = new Image();
      img.onload = () => {
        canvas.width = img.width;
        canvas.height = img.height;
        ctx.drawImage(img, 0, 0);

        let annotationIndex = 1;
        Object.values(results.sections).forEach(section => {
          section.findings.forEach(finding => {
            if (finding.bbox) {
              const { x, y, w, h } = finding.bbox;
              
              ctx.strokeStyle = finding.type === 'improvement' ? '#f59e0b' : '#10b981';
              ctx.lineWidth = 3;
              ctx.strokeRect(x, y, w, h);
              
              ctx.fillStyle = finding.type === 'improvement' ? '#f59e0b' : '#10b981';
              ctx.fillRect(x, y - 25, 30, 25);
              
              ctx.fillStyle = '#ffffff';
              ctx.font = 'bold 14px Arial';
              ctx.textAlign = 'center';
              ctx.textBaseline = 'middle';
              ctx.fillText(annotationIndex.toString(), x + 15, y - 12);
              
              annotationIndex++;
            }
          });
        });
      };
      img.src = uploadedImage;
    }
  }, [uploadedImage, results, showAnnotations]);

  const downloadAnnotatedImage = () => {
    if (!canvasRef.current) return;
    const url = canvasRef.current.toDataURL('image/png');
    const a = document.createElement('a');
    a.href = url;
    a.download = `${fileName.split('.')[0]}_annotated.png`;
    a.click();
  };

  return (
    <div className="flex h-screen bg-gray-50">
      {/* Left Sidebar */}
      <div className="w-64 bg-white border-r border-gray-200 p-6 flex flex-col">
        <div className="flex items-center space-x-2 mb-8">
          <div className="w-8 h-8 bg-indigo-600 rounded-lg flex items-center justify-center">
            <span className="text-white font-bold text-lg">U</span>
          </div>
          <h1 className="text-xl font-bold text-gray-900">UX WISE AI</h1>
        </div>

        <div className="flex-1 space-y-6">
          <div>
            <h2 className="text-sm font-semibold text-gray-900 mb-3">Design Analysis</h2>
            <div className="space-y-3">
              <div>
                <label className="text-xs text-gray-600 mb-1 block">Upload Design</label>
                <div
                  onDragOver={handleDragOver}
                  onDrop={handleDrop}
                  onClick={() => fileInputRef.current?.click()}
                  className="border-2 border-dashed border-gray-300 rounded-lg p-4 text-center cursor-pointer hover:border-indigo-400 transition-colors"
                >
                  {uploadedImage ? (
                    <div className="space-y-2">
                      <img src={uploadedImage} alt="Preview" className="w-full h-24 object-cover rounded" />
                      <p className="text-xs text-gray-600 truncate">{fileName}</p>
                      <p className="text-xs text-gray-400">0.58 MB</p>
                    </div>
                  ) : (
                    <div className="space-y-2">
                      <Upload className="w-8 h-8 mx-auto text-gray-400" />
                      <p className="text-xs text-gray-600">Drop file or click to upload</p>
                    </div>
                  )}
                </div>
                <input
                  ref={fileInputRef}
                  type="file"
                  accept="image/*"
                  onChange={handleFileUpload}
                  className="hidden"
                />
              </div>

              <div>
                <label className="text-xs text-gray-600 mb-1 block">Mode</label>
                <select
                  value={mode}
                  onChange={(e) => setMode(e.target.value)}
                  className="w-full px-3 py-2 border border-gray-300 rounded-lg text-sm focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500"
                >
                  <option value="direct">Direct</option>
                  <option value="guided">Guided</option>
                  <option value="strict">Strict</option>
                </select>
                <p className="text-xs text-gray-500 mt-1">Balanced approach with practical implementation suggestions</p>
              </div>

              <div>
                <label className="text-xs text-gray-600 mb-2 block">Analysis Aspects</label>
                <div className="space-y-2">
                  <Checkbox
                    checked={aspects.uxStandards}
                    onChange={(e: any) => setAspects({ ...aspects, uxStandards: e.target.checked })}
                    label="UX Standards (Required)"
                  />
                  <Checkbox
                    checked={aspects.accessibility}
                    onChange={(e: any) => setAspects({ ...aspects, accessibility: e.target.checked })}
                    label="Accessibility Compliance"
                  />
                  <Checkbox
                    checked={aspects.culturalDiversity}
                    onChange={(e: any) => setAspects({ ...aspects, culturalDiversity: e.target.checked })}
                    label="Cultural Diversity"
                  />
                  <Checkbox
                    checked={aspects.privacySecurity}
                    onChange={(e: any) => setAspects({ ...aspects, privacySecurity: e.target.checked })}
                    label="Privacy and Security"
                  />
                  <Checkbox
                    checked={aspects.visualConsistency}
                    onChange={(e: any) => setAspects({ ...aspects, visualConsistency: e.target.checked })}
                    label="Visual Consistency"
                  />
                  <Checkbox
                    checked={aspects.heuristicFeedback}
                    onChange={(e: any) => setAspects({ ...aspects, heuristicFeedback: e.target.checked })}
                    label="Heuristic Feedback"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>

        <div className="space-y-3">
          <Button
            onClick={handleAnalyze}
            disabled={!uploadedImage}
            className="w-full"
          >
            Analyze Design
          </Button>
          <p className="text-xs text-gray-500 text-center">AI output may be inaccurate</p>
        </div>
      </div>

      {/* Main Content Area */}
      <div className="flex-1 overflow-auto">
        {results ? (
          <div className="p-8">
            {/* Header */}
            <div className="flex items-center justify-between mb-6">
              <div>
                <h2 className="text-2xl font-bold text-gray-900">Analysis Results</h2>
                <p className="text-sm text-gray-600">Here's the UX analysis generated by AI:</p>
              </div>
              <div className="flex items-center space-x-3">
                <Button
                  variant="outline"
                  onClick={() => exportToExcel(results, 'ux-analysis.csv')}
                  className="flex items-center space-x-2"
                >
                  <Table className="w-4 h-4" />
                  <span>Export as Excel</span>
                </Button>
                <div className="relative">
                  <Button
                    variant="ghost"
                    onClick={() => setShowExportMenu(!showExportMenu)}
                  >
                    <MoreVertical className="w-5 h-5" />
                  </Button>
                  {showExportMenu && (
                    <div className="absolute right-0 mt-2 w-56 bg-white rounded-lg shadow-lg border border-gray-200 py-1 z-10">
                      <button
                        onClick={() => { exportToJSON(results, 'ux-analysis.json'); setShowExportMenu(false); }}
                        className="w-full px-4 py-2 text-left text-sm hover:bg-gray-50 flex items-center space-x-2"
                      >
                        <FileText className="w-4 h-4" />
                        <span>Export JSON</span>
                      </button>
                      <button
                        onClick={() => { exportToExcel(results, 'ux-analysis.csv'); setShowExportMenu(false); }}
                        className="w-full px-4 py-2 text-left text-sm hover:bg-gray-50 flex items-center space-x-2"
                      >
                        <Table className="w-4 h-4" />
                        <span>Export CSV</span>
                      </button>
                      <button
                        onClick={() => { downloadAnnotatedImage(); setShowExportMenu(false); }}
                        className="w-full px-4 py-2 text-left text-sm hover:bg-gray-50 flex items-center space-x-2"
                      >
                        <ImageIcon className="w-4 h-4" />
                        <span>Download Annotated Images</span>
                      </button>
                      <button
                        onClick={() => { handleReset(); setShowExportMenu(false); }}
                        className="w-full px-4 py-2 text-left text-sm hover:bg-gray-50 text-red-600"
                      >
                        Reset
                      </button>
                    </div>
                  )}
                </div>
              </div>
            </div>

            <div className="grid grid-cols-1 lg:grid-cols-2 gap-6">
              {/* Results Cards */}
              <div className="space-y-4">
                {Object.entries(results.sections).map(([key, section]) => (
                  <Card key={key} className="overflow-hidden">
                    <div className="p-4">
                      <div className="flex items-center justify-between mb-3">
                        <div className="flex items-center space-x-3">
                          <h3 className="font-semibold text-gray-900">{section.name}</h3>
                          <Badge variant={section.score >= 80 ? 'success' : section.score >= 60 ? 'warning' : 'default'}>
                            Score: {section.score}/100
                          </Badge>
                        </div>
                        <div className="flex items-center space-x-2">
                          <button
                            onClick={() => copySection(key)}
                            className="p-1 hover:bg-gray-100 rounded"
                          >
                            {copiedSection === key ? <Check className="w-4 h-4 text-green-600" /> : <Copy className="w-4 h-4 text-gray-600" />}
                          </button>
                          <button
                            onClick={() => toggleSection(key)}
                            className="p-1 hover:bg-gray-100 rounded"
                          >
                            {expandedSections[key] ? <ChevronUp className="w-4 h-4" /> : <ChevronDown className="w-4 h-4" />}
                          </button>
                        </div>
                      </div>

                      <Progress value={section.score} className="mb-4" />

                      {expandedSections[key] && (
                        <div className="space-y-4">
                          {section.findings.filter(f => f.type === 'strength').length > 0 && (
                            <div>
                              <div className="flex items-center space-x-2 mb-2">
                                <div className="w-2 h-2 bg-green-500 rounded-full" />
                                <h4 className="text-sm font-medium text-gray-700">Strengths</h4>
                              </div>
                              <ul className="space-y-1 ml-4">
                                {section.findings.filter(f => f.type === 'strength').map(finding => (
                                  <li key={finding.id} className="text-sm text-gray-600">• {finding.message}</li>
                                ))}
                              </ul>
                            </div>
                          )}

                          {section.findings.filter(f => f.type === 'improvement').length > 0 && (
                            <div>
                              <div className="flex items-center space-x-2 mb-2">
                                <div className="w-2 h-2 bg-orange-500 rounded-full" />
                                <h4 className="text-sm font-medium text-gray-700">Improvement Opportunities</h4>
                              </div>
                              <ul className="space-y-1 ml-4">
                                {section.findings.filter(f => f.type === 'improvement').map(finding => (
                                  <li key={finding.id} className="text-sm text-gray-600">• {finding.message}</li>
                                ))}
                              </ul>
                            </div>
                          )}

                          {section.patterns && section.patterns.length > 0 && (
                            <div>
                              <h4 className="text-sm font-medium text-gray-700 mb-2">Design Patterns</h4>
                              <div className="flex flex-wrap gap-2">
                                {section.patterns.map((pattern, idx) => (
                                  <Badge key={idx} variant="purple">{pattern}</Badge>
                                ))}
                              </div>
                            </div>
                          )}
                        </div>
                      )}
                    </div>
                  </Card>
                ))}
              </div>

              {/* Annotated Preview */}
              <div className="sticky top-8">
                <Card className="p-4">
                  <div className="flex items-center justify-between mb-3">
                    <h3 className="font-semibold text-gray-900">Annotated Preview</h3>
                    <div className="flex items-center space-x-2">
                      <Checkbox
                        checked={showAnnotations}
                        onChange={(e: any) => setShowAnnotations(e.target.checked)}
                        label="Show Annotations"
                      />
                      <Button
                        variant="outline"
                        onClick={downloadAnnotatedImage}
                        className="flex items-center space-x-1 !px-3 !py-1"
                      >
                        <Download className="w-4 h-4" />
                        <span className="text-xs">Download</span>
                      </Button>
                    </div>
                  </div>
                  <div className="bg-gray-50 rounded-lg overflow-hidden">
                    <canvas ref={canvasRef} className="w-full h-auto" />
                  </div>
                </Card>
              </div>
            </div>
          </div>
        ) : (
          <div className="h-full flex items-center justify-center text-gray-400">
            <div className="text-center">
              <Upload className="w-16 h-16 mx-auto mb-4" />
              <p className="text-lg font-medium">Upload a design to get started</p>
              <p className="text-sm mt-2">Drag and drop or click to upload in the left sidebar</p>
            </div>
          </div>
        )}
      </div>
    </div>
  );
}
