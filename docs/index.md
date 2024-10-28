# MultiversX Snapshotless Observing Squad Deployment Guide

This tutorial provides a step-by-step guide to setting up a MultiversX Snapshotless Observing Squad using Alibaba Cloud Compute Nest, and ECS. 

## Introduction

## Prerequisites
Before starting, ensure you have:

An active Alibaba Cloud account.
Familiarity with cloud services.

## Step 1: Alibaba Cloud Account Setup
If you haven't already, sign up for an Alibaba Cloud account: Sign up (https://www.alibabacloud.com).

## Step 2: Access Compute Nest
Navigate to Compute Nest and locate the service for MultiversX Snapshotless Observing Squad

## Step 3: Set Up an Instance and Its Parameters
Configure the necessary parameters for the instance

Service Instance Name: Provide a meaningful name for the instance.
Instance Password: Create a secure password for the instance.

## Step 4: Deploy Your RAG Service
Review all configurations and accept the Terms of Service. Click Create Now to deploy your service.

## Step 5: Integrate with the MultiversX Network
Description:
In order to integrate with the MultiversX Network and be able to broadcast transactions and query blockchain data in an optimized approach, one needs to set up an on-premises Observing Squad. An Observing Squad is defined as a set of N Observer Nodes (one for each Shard, including the Metachain) plus an MultiversX Proxy instance which will connect to these Observers and provide an HTTP API (by delegating requests to the Observers).
The snapshotless mode allows you to quickly synchronize with the network and perform Rest API calls for retrieving real-time data from the blockchain, such as getting data of an address (GET /address/${address}), getting the balance of an address (GET /address/${address}/balance), sending transactions, performing Smart Contract Queries and many more .
Full List of supported Operations can be found here : https://docs.multiversx.com/sdk-and-tools/proxy/#snaphotless-observers-support

Getting started after deploying MultiversX Observing Squad
A systemd service will start docker compose and run all the Multiversx Observers shards in snapshotless mode .
Make sure to allow port 22 and 8079 in your security group settings.
The following tools are available at this path : /opt/multiversx-observing-squad-tools/
```
./stop_stack.sh      #-- stops the observing squad stack
./start_stack.sh     #-- starts the observing squad stack
./check_stack_sync_status.sh    #-- get node syncronization status
./check_stack_node_version.sh   #-- get stack version information
./upgrade_stack.sh   #-- upgrade stack version
```
Once the stack is in sync you can query the proxy for information :
```
curl -s -k localhost:8079/network/config
```
Or via the public ip address of your instance on port 8079.
Full list of supported operations in snapshotless mode can be found here: https://docs.multiversx.com/sdk-and-tools/proxy/#snaphotless-observers-support

## Conclusion
This tutorial has guided you through the comprehensive process of building a MultiversX Snapshotless Observing Squad service using Alibaba Cloud Compute Nest, and ECS. Following these steps will help you to quickly deploy MultiversX Snapshotless Observing Squad services on Alibaba Cloud
