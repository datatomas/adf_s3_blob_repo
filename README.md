# Multi-Cloud ETL with Azure Data Factory (S3 to Blob) + Joins

This repository contains an example Azure Data Factory (ADF) project that builds a multi-cloud ETL pipeline using AWS S3 as the source and Azure Blob Storage as the sink. The pipeline merges multiple files using Copy Activity and performs a left join transformation using ADF Data Flows.

## What it does
- Connects ADF to AWS S3 using IAM access keys
- Connects ADF to Azure Blob Storage using Managed Identity
- Copies all CSV files from an S3 folder into Azure Blob and merges them into one file
- Uses Data Flow to left join datasets and generate an enriched output table
- Supports tagging conventions for cost allocation across environments
- Optional GitHub integration for version control and CI/CD

## Prerequisites
- Azure Data Factory instance
- AWS S3 bucket with input files
- IAM user with S3 permissions
- Azure Storage account (Blob or ADLS Gen2)
- Permissions to assign Storage Blob Data roles to ADF managed identity

## Repository contents
- `main.bicep` Azure Storage infrastructure template
- ADF pipeline and Data Flow design notes (follow the steps in the tutorial)

## Notes
For production deployments, prefer private endpoints and temporary AWS credentials instead of long-lived access keys.
