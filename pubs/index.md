---
layout: page
title: Publications
tags:
comments: false
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Publications</title>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            color: #333;
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px;
            background-color: #fafafa;
        }

        .section {
            background: white;
            border-radius: 12px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .section:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.15);
        }

        .section-header {
            font-size: 1.5em;
            font-weight: bold;
            color: #27ae60;
            margin-bottom: 25px;
            text-align: center;
            padding: 10px;
            background: linear-gradient(135deg, #f0f9f0 0%, #d5e8d5 100%);
            border-radius: 10px;
            border-left: 4px solid #27ae60;
        }

        .publication-item {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 15px;
            border-left: 4px solid #27ae60;
            transition: all 0.3s ease;
        }

        .publication-item:hover {
            background: #f0f9f0;
            transform: translateX(5px);
        }

        .publication-item:last-child {
            margin-bottom: 0;
        }

        .publication-text {
            font-size: 1.05em;
            line-height: 1.7;
        }

        .publication-text a {
            color: #27ae60;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .publication-text a:hover {
            color: #1e8449;
            text-decoration: underline;
        }

        .journal-name {
            font-style: italic;
            color: #2c3e50;
            font-weight: 500;
        }

        .author-highlight {
            font-weight: bold;
            color: #27ae60;
        }

        .doi-link {
            display: inline-block;
            background: #e8f5e8;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 0.9em;
            margin-top: 5px;
            transition: all 0.3s ease;
        }

        .doi-link:hover {
            background: #27ae60;
            color: white;
        }

        @media (max-width: 768px) {
            body {
                padding: 10px;
            }

            .section {
                padding: 20px;
            }

            .section-header {
                font-size: 1.6em;
                padding: 10px;
            }

            .publication-item {
                padding: 15px;
            }
        }
    </style>
</head>
<body>
    <div class="section">
        <div class="section-header">Papers</div>
        
        <div class="publication-item">
            <div class="publication-text">
                Hanrahan, J., A. Maynard, <span class="author-highlight">S.Y. Murphy</span>, C. Zercher, and A. Fitzpatrick, 2017: 
                <a href="https://journals.ametsoc.org/jamc/article/56/10/2869/20343/Examining-the-Climatology-of-Shortwave-Radiation">Examining the Climatology of Shortwave Radiation in the Northeastern United States.</a> 
                <span class="journal-name">J. Appl. Meteor. Climatol.</span>, 56, 2869–2881, 
                <a href="https://doi.org/10.1175/JAMC-D-16-0420.1" class="doi-link">https://doi.org/10.1175/JAMC-D-16-0420.1</a>
            </div>
        </div>

        <div class="publication-item">
            <div class="publication-text">
                Walden, V. P., Hudson, S. R., Cohen, L., <span class="author-highlight">Murphy, S. Y.</span>, and Granskog, M. A. (2017), 
                <a href="https://agupubs.onlinelibrary.wiley.com/doi/full/10.1002/2016JD026091">Atmospheric components of the surface energy budget over young sea ice: Results from the N‐ICE2015 campaign.</a> 
                <span class="journal-name">J. Geophys. Res. Atmos.</span>, 122, 8427–8446, 
                <a href="https://doi.org/10.1002/2016JD026091" class="doi-link">doi:10.1002/2016JD026091</a>
            </div>
        </div>
    </div>

    <div class="section">
        <div class="section-header">Datasets</div>
        
        <div class="publication-item">
            <div class="publication-text">
                Walden, V. P., <span class="author-highlight">Murphy, S.</span>, Hudson, S. R., & Cohen, L. (2017). 
                <a href="https://doi.org/10.21334/npolar.2017.298013b7">N-ICE2015 atmospheric turbulent fluxes [Data set].</a> 
                Norwegian Polar Institute. 
                <a href="https://doi.org/10.21334/npolar.2017.298013b7" class="doi-link">https://doi.org/10.21334/npolar.2017.298013b7</a>
            </div>
        </div>
    </div>
</body>
</html>
