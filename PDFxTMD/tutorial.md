---
layout: pdfxtmd_default
title: Tutorial
---

<div class="container mt-4">
    <div class="row">
        <div class="col-12">
            <div class="card mb-4">
                <div class="card-header">
                    <h2>How to Use PDFxTMD on Linux</h2>
                </div>
                <div class="card-body">
                    <p>Let's assume you want to calculate a collinear PDF (cPDF) using the MMHT2014lo68cl PDF set. You can write this program:</p>

{% highlight cpp %}
#include <iostream>
#include <PDFxTMDLib/Factory.h>

int main()
{
    using namespace PDFxTMD;
    // Use CPDFFactory class for collinear PDF factory
    GenericCPDFFactory cPDF;
    // Specify PDF set name and set member in mkCPDF method
    auto CJ12min = cPDF.mkCPDF("MMHT2014lo68cl", 0);
    double x = 0.01;
    double mu2 = 100;
    // Calculate up quark at x and mu^2
    std::cout << CJ12min.pdf(PartonFlavor::u, x, mu2) << std::endl;
    return 0;
}
{% endhighlight %}

                    <p>To compile this code, you have two options: using CMake or direct linking.</p>

                    <h3 class="mt-4">1. Using CMakeLists (Preferred Approach)</h3>
                    <p>To use CMakeLists, you only need to link against PDFxTMDLib::PDFxTMDLib. Assume that your code is written in a file called "main.cpp". With this CMakeLists.txt file, you can easily build the program:</p>

{% highlight cmake %}
cmake_minimum_required(VERSION 3.22)
project(testPDFxTMD LANGUAGES CXX)

find_package(PDFxTMDLib REQUIRED)
add_executable(pdf_example main.cpp)
target_link_libraries(pdf_example PRIVATE PDFxTMDLib::PDFxTMDLib)
{% endhighlight %}

                    <div class="alert alert-info mt-4">
                        <strong>Note:</strong> If you're unfamiliar with CMake, leave a comment below.
                    </div>
                    <h3 class="mt-4">2. Direct Linking</h3>
                    <p>To compile the program using direct linking, use the following command:</p>
                    <pre><code>g++ main.cpp -I/usr/include/PDFxTMDLib -L/usr/lib -lPDFxTMDLib</code></pre>
                    <p>In this command, it is assumed that the PDFxTMDLib include files are located at <code>/usr/include/</code>, and the library is located at <code>/usr/lib/</code> with the name <code>libPDFxTMDLib.so</code>.</p>
                </div>
                
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