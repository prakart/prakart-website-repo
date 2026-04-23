---
title: 'Deployment Summary: Hostinger & GitHub CI/CD'
publishDate: 2026-04-23
updatedDate: 2026-04-23
description: 'a summary of the tasks, technical challenges, and solutions from our deployment session'
tags:
  - CI/CD
  - DevOps
language: 'English'
heroImage: { src: './thumbnail.jpg', color: '#D58388' }
---

### **Deployment Summary: Hostinger & GitHub CI/CD**

**1\. Primary Objective**

*   Successfully deploy the local Astro project to a live production environment on Hostinger using automated GitHub-based deployment.
    

**2\. Key Technical Activities**

*   **Static Build Configuration:** Successfully configured the Astro project for static site generation (SSG) to ensure compatibility with standard web hosting.
    
*   **Production Build Validation:** Ran npm run build to generate the production dist/ folder, identifying and resolving dependency and code-level errors.
    
*   **CI/CD Pipeline Setup:** Connected the GitHub repository to Hostinger’s built-in deployment service using SSH Deploy Keys.
    
*   **Output Directory Mapping:** Configured the deployment settings to ensure the server correctly identifies and moves the dist/ folder to the live public\_html directory.
    

**3\. Problems Encountered & Solutions**

*   **Build Crash (Cannot read properties of undefined):** \* _Problem:_ The production build is "strict" and crashed because the code was attempting to access properties (.toString()) on missing or empty data objects in the projects list.
    
    *   _Solution:_ Implemented "Guard Clauses" and "Optional Chaining" (?.) in ProjectSection.astro to safely handle missing project data without crashing the build engine.
        
*   **Development vs. Production Discrepancy:**
    
    *   _Problem:_ The site worked on localhost but failed during npm run build.
        
    *   _Resolution:_ Recognized that local development environments are "forgiving" (only rendering what is visited), whereas production builds perform a "full coverage" check of all pages.
        
*   **Deployment Script Error (No output directory found):**
    
    *   _Problem:_ Hostinger couldn't locate the generated build artifacts.
        
    *   _Solution:_ Explicitly mapped the "Output Directory" setting in Hostinger hPanel to match the project's dist folder.
        

**4\. Current Status**

*   **Deployment:** Successfully live.
    
*   **Workflow:** Automated via GitHub push.
    
*   **Immediate Next Steps:** Review the project list on the site; fix the individual project data entries that triggered the original build errors so they can be safely uncommented and displayed.


Here is a summary of the tasks, technical challenges, and solutions from our deployment session today, organized for your notes:

## Deployment Summary: Hostinger & GitHub CI/CD

Put simply, 3D rendering is the process of using a computer to generate a 2D image from a digital three-dimensional scene.

To generate an image, specific methodologies and special software and hardware are used. Therefore, we need to understand that 3D rendering is a process—the one that builds the image.

![alt text](./nikola-arsov-still-life-interior-design-vray-3ds-max-05-930px.jpg)

## Types of 3D rendering

We can create different types of rendered image; they can be realistic or non-realistic.

A realistic image could be an architectural interior that looks like a photograph, a product-design image such as a piece of furniture, or an automotive rendering of a car. On the other hand, we can create a non-realistic image such as an outline-type diagram or a cartoon-style image with a traditional 2D look. Technically, we can visualize anything we can imagine.

## How is 3D rendering used?

3D rendering is an essential technique for many industries including architecture, product design, advertising, video games and visual effects for film, TV and animation.

In design and architecture, renders allow creative people to communicate their ideas in a clear and transparent way. A render gives them the chance to evaluate their proposals, experiment with materials, conduct studies and contextualize their designs in the real world before they are built or manufactured.

For the media and entertainment industries, 3D rendering is fundamental to the creation of sequences and animations that tell stories, whether we’re watching an animated movie, a period drama, or an action sequence with explosions, ships from the future, exotic locales, or extraterrestrial creatures.

![alt text](./thanos-dd-single-image-004a.jpg)

Over the past few years, the evolution of computer graphics in these industries has replaced traditional techniques. For example, special effects are being replaced by visual effects, which means stunt people no longer risk their lives in car crashes.

In advertising, I would dare to say that 90% of automotive commercials are CG—or even more. In the architecture industry, many traditional techniques to create representations, such as scale models, have been replaced with photorealistic imagery to ensure we can see exactly how something will look once it’s built.

Accelerating processes, reducing costs and the demand for better quality results have helped technology evolve. Hardware is more powerful than ever and the switch to CG was inevitable.

## How is a 3D rendered image generated?

Two pieces of software, with different characteristics, are used to computer-generate images and animations: render engines and game engines. Render engines use a technique called ray tracing, while game engines use a technique called rasterization—and some engines mix both techniques, but we will talk about that later on.
