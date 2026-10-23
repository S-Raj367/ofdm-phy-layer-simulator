
<h1>OFDM Communication System in C++</h1>

<h2>Overview</h2>
<p>
  This project implements a simplified Orthogonal Frequency Division
  Multiplexing (OFDM) system in C++. It explores digital modulation,
  wireless channel estimation, and error-correction techniques used
  in communication systems.
</p>

<h2>Features</h2>

<h3>1. Digital Modulation</h3>
<ul>
  <li>BPSK</li>
  <li>QPSK</li>
  <li>16-QAM</li>
</ul>

<p>
  These modulation schemes can be used to study the effects of
  different modulation orders on communication performance.
</p>

<h3>2. Channel Estimation</h3>
<ul>
  <li>
    <strong>Least Squares (LS):</strong>
    Estimates the channel response using known pilot symbols.
  </li>
  <li>
    <strong>Minimum Mean Square Error (MMSE):</strong>
    Uses statistical information about the channel and noise
    to minimize expected estimation error.
  </li>
  <li>
    <strong>Linear Minimum Mean Square Error (LMMSE):</strong>
    Applies a linear estimator based on channel and noise statistics.
  </li>
</ul>

<h3>3. Error-Correction Coding</h3>
<ul>
  <li>
    <strong>(7,4) Hamming Code:</strong>
    Adds redundancy to support single-bit error correction.
  </li>
  <li>
    <strong>Rate-1/2 Convolutional Code:</strong>
    Encodes input bits into a redundant bitstream.
    Hard-decision decoding uses Hamming distance as its metric.
  </li>
</ul>

<h2>Technologies and Dependencies</h2>
<ul>
  <li>C++14</li>
  <li>MATLAB R2022b</li>
  <li>FFTW3 for Fourier Transform operations</li>
  <li>Eigen for linear algebra</li>
  <li>MATLAB Data API</li>
  <li>Google Test for unit testing</li>
  <li>CMake for project configuration</li>
</ul>

<h2>Building and Running</h2>
<p>
  Install and configure the required dependencies before building
  the project.
</p>

<pre><code>mkdir build
cd build
cmake ..
make
./ofdm</code></pre>

<p>
  Build commands may vary depending on the operating system and
  installed dependencies.
</p>

<h2>Testing</h2>
<p>
  Google Test is used to test components of the error-correction
  implementation. To run the available tests, navigate to the
  test directory and execute:
</p>

<pre><code>./test.sh</code></pre>

<h2>OFDM Fundamentals</h2>

<h3>Cyclic Prefix</h3>
<p>
  A cyclic prefix is created by copying the end portion of an OFDM
  symbol to its beginning. When sufficiently long, it helps reduce
  inter-symbol interference and allows the channel's linear
  convolution to be treated as circular convolution over the useful
  symbol interval.
</p>

<h3>FFT and IFFT</h3>
<p>
  OFDM distributes data across multiple orthogonal subcarriers.
  The Inverse Fast Fourier Transform (IFFT) converts the modulated
  subcarrier symbols into a time-domain signal at the transmitter.
  The Fast Fourier Transform (FFT) separates the subcarriers at
  the receiver.
</p>

<h3>Pilot-Based Channel Estimation</h3>
<p>
  Known pilot symbols help the receiver estimate the wireless
  channel response. For a pilot subcarrier, the Least Squares
  estimate is:
</p>

<p>
  <code>H_hat(k) = Y(k) / X(k)</code>
</p>

<p>
  Here, X(k) represents the transmitted pilot and Y(k) represents
  the received pilot. MMSE-based approaches additionally use
  statistical information about the channel and noise.
</p>

<h2>Performance Evaluation</h2>
<ul>
  <li>Bit Error Rate (BER)</li>
  <li>Symbol Error Rate (SER)</li>
  <li>Channel estimation error</li>
  <li>Performance at different signal-to-noise ratios</li>
</ul>

<h2>Further Reading</h2>
<ul>
  <li>
    <a href="https://nptel.ac.in/courses/117104118">
      NPTEL: Digital Communication
    </a>
  </li>
  <li>
    <a href="https://www.nxp.com/docs/en/application-note/AN3059.pdf">
      NXP Application Note AN3059
    </a>
  </li>
</ul>

<h2>Notes</h2>
<p>
  This project provides a framework for studying OFDM fundamentals
  and comparing modulation, channel estimation, and error-correction
  techniques. Results depend on the simulation parameters, channel
  model, and implementation details.
</p>
