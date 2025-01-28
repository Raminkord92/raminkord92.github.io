---
layout: pdfxtmd_default
title: Installation Guide
---

<div class="container mt-4">
    <div class="row">
        <div class="col-md-8">
            <!-- System Requirements -->
            <div class="card shadow-sm mb-4">
                <div class="card-header bg-primary text-white">
                    <h3 class="mb-0"><i class="fas fa-server mr-2"></i>System Requirements</h3>
                </div>
                <div class="card-body">
                    <div class="row mb-4">
                        <div class="col-md-6">
                            <h5>Core Dependencies</h5>
                            <ul class="list-group list-group-flush">
                                <li class="list-group-item d-flex justify-content-between align-items-center">
                                    GNU Scientific Library (GSL)
                                </li>
                                <li class="list-group-item d-flex justify-content-between align-items-center">
                                    libcurl
                                </li>
                            </ul>
                        </div>
                        <div class="col-md-6">
                            <h5>Build Requirements</h5>
                            <ul class="list-group list-group-flush">
                                <li class="list-group-item">
                                    C++ Compiler
                                    <span class="badge badge-secondary">C++17</span>
                                </li>
                            </ul>
                        </div>
                    </div>

                    <!-- Optional Features -->
                    <div class="alert alert-secondary">
                        <h5><i class="fas fa-cubes"></i> Optional Features</h5>
                        <dl class="row">
                            <dt class="col-sm-3">Python Bindings</dt>
                            <dd class="col-sm-9">
                                <ul class="list-unstyled">
                                    <li>Requires Python 3.8+</li>
                                </ul>
                            </dd>
                            
                            <dt class="col-sm-3">Fortran Modules</dt>
                            <dd class="col-sm-9">
                                <ul class="list-unstyled">
                                    <li>Requires gfortran (Linux) or Intel Fortran</li>
                                </ul>
                            </dd>
                        </dl>
                    </div>

                    <!-- Platform Tabs -->
                    <ul class="nav nav-tabs" id="platformTabs" role="tablist">
                        <li class="nav-item">
                            <a class="nav-link active" id="linux-tab" data-toggle="tab" href="#linux" role="tab">
                                <i class="fab fa-linux"></i> Ubuntu/Debian
                            </a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" id="windows-tab" data-toggle="tab" href="#windows" role="tab">
                                <i class="fab fa-windows"></i> Windows
                            </a>
                        </li>
                    </ul>

                    <div class="tab-content mt-3">
                        <!-- Linux Instructions -->
                        <div class="tab-pane fade show active" id="linux" role="tabpanel">
                            <pre>
                                <code class="language-bash">
# Core dependencies
sudo apt-get update
sudo apt-get install -y g++ libgsl-dev  libcurl4-openssl-dev 

# Optional: Python support
sudo apt-get install -y python3-dev

# Optional: Fortran support
sudo apt-get install -y gfortran
                                </code>
                            </pre>
                        </div>

                        <!-- Windows Instructions -->
                        <div class="tab-pane fade" id="windows" role="tabpanel">
                            <pre>
                                <code class="language-powershell">
# Core dependencies
vcpkg install gsl:x64-windows curl:x64-windows

# Optional: Python support
vcpkg install python3:x64-windows

# Environment setup (assuming, vcpkg is installed in C:\)
$env:CMAKE_TOOLCHAIN_FILE = "C:\vcpkg\scripts\buildsystems\vcpkg.cmake"
                                </code>
                            </pre>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Installation Steps -->
            <div class="card shadow-sm mb-4">
                <div class="card-header bg-success text-white">
                    <h3 class="mb-0"><i class="fas fa-download mr-2"></i>Installation Steps</h3>
                </div>
                <div class="card-body">
                    <div class="mb-4">
                        <h4 class="text-success"><i class="fas fa-terminal"></i> Build Commands</h4>
                        <pre><code class="language-bash">
git clone https://github.com/yourusername/pdfxtmd.git
cd pdfxtmd
mkdir build
cd build

# Basic configuration
cmake .. -DCMAKE_BUILD_TYPE=Release

# Build & Install
cmake --build . --config Release
sudo make install  # Linux
                        </code></pre>
                    </div>

                    <!-- Verification -->
                    <div class="alert alert-success">
                        <h5><i class="fas fa-check-circle"></i> Verify Installation</h5>
                        <pre class="mb-0"><code class="language-bash">
# Basic verification in Windows from root folder
.\build\examples\Release\pdf_example.exe
# Basic verification in Linux from root folder
./build/examples/pdf_example
                        </code></pre>
                    </div>
                </div>
            </div>

            <!-- Giscus Comments -->
            <script src="https://giscus.app/client.js"
            data-repo="Raminkord92/raminkord92.github.io"
            data-repo-id="R_kgDONwvdSw"
            data-category="Comments"
            data-category-id="DIC_kwDONwvdS84CmaRl"
            data-mapping="pathname"
            data-theme="light"
            crossorigin="anonymous"
            async>
            </script>
        </div>
    </div>
</div>