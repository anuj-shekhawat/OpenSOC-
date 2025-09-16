# OpenSOC Integration Guide

This guide explains how to integrate all components of your OpenSOC PoC according to the architecture diagram. Screenshots and commands are included for clarity.

---

## Table of Contents

1. [ELK → TheHive](#elk--thehive)  
2. [TheHive → Cortex](#thehive--cortex)  
3. [TheHive → MISP](#thehive--misp)  
4. [Cortex → MISP](#cortex--misp)  

---

## ELK → TheHive

### 1. Create a webhook in ELK  

- **Content-Type:** `application/json`  
- **Authorization:** `Bearer API-KEY`  


### 2. Generate an API key in TheHive  

- Log in to TheHive as an admin.  
- Create a new user and assign the **Org-Admin Role**.  
- Generate an API key for this user.  


### 3. Test the webhook  

Send the following JSON payload to create a test case:

```json
{
  "title": "My Auto case",
  "description": "A VPN user has connected from a foreign country",
  "tlp": 3,
  "tags": ["automatic", "creation"]
}

----


## TheHive → Cortex


### 1. Create a Cortex user

- Log in to Cortex UI.  
- Create a new user with **Org-Admin Role**.  
- Generate an API key.  

---

### 2. Configure Cortex in TheHive

SSH into TheHive server and edit `/etc/thehive/application.conf`:

```hocon
cortex {
  servers: [
    {
      name: "Cortex1"
      url: "http://Cortex-VM-IP:9001"
      auth {
        type: "bearer"
        key: "PASTE_YOUR_NEW_API_KEY"
      }
    }
  ]
}

