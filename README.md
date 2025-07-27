# firtsagent-testing{
  "name": "My workflow",
  "nodes": [
    {
      "parameters": {
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.chatTrigger",
      "typeVersion": 1.1,
      "position": [
        -352,
        -16
      ],
      "id": "649e1101-3bdf-4ef6-b2ba-6d94868f1458",
      "name": "When chat message received",
      "webhookId": "bb947b7b-f831-4146-83af-156e5eb13788"
    },
    {
      "parameters": {
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.agent",
      "typeVersion": 2.1,
      "position": [
        -144,
        -16
      ],
      "id": "975fd770-36b5-4287-b898-e8de79223ad3",
      "name": "AI Agent"
    },
    {
      "parameters": {
        "model": {
          "__rl": true,
          "value": "gpt-4o-mini",
          "mode": "list",
          "cachedResultName": "gpt-4o-mini"
        },
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.lmChatOpenAi",
      "typeVersion": 1.2,
      "position": [
        -416,
        208
      ],
      "id": "7f46cb07-0e7b-46ec-b587-d34b39186fa6",
      "name": "OpenAI Chat Model",
      "credentials": {
        "openAiApi": {
          "id": "eKYobeSxxyvLxpwq",
          "name": "OpenAi account"
        }
      }
    },
    {
      "parameters": {},
      "type": "@n8n/n8n-nodes-langchain.memoryBufferWindow",
      "typeVersion": 1.3,
      "position": [
        -256,
        272
      ],
      "id": "29009b36-c442-4bcd-b873-9af26dd787ed",
      "name": "Simple Memory"
    },
    {
      "parameters": {},
      "type": "@n8n/n8n-nodes-langchain.toolCalculator",
      "typeVersion": 1,
      "position": [
        224,
        224
      ],
      "id": "ea5b26e0-6c60-4a2f-b0e2-cb896e9f8e43",
      "name": "Calculator"
    },
    {
      "parameters": {
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.toolSerpApi",
      "typeVersion": 1,
      "position": [
        0,
        288
      ],
      "id": "97eec664-f38f-4c7a-a2fb-de6567c3bfe5",
      "name": "SerpAPI",
      "credentials": {
        "serpApi": {
          "id": "XhXq4RBjnFhp3vwS",
          "name": "SerpAPI account"
        }
      }
    }
  ],
  "pinData": {},
  "connections": {
    "When chat message received": {
      "main": [
        [
          {
            "node": "AI Agent",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "OpenAI Chat Model": {
      "ai_languageModel": [
        [
          {
            "node": "AI Agent",
            "type": "ai_languageModel",
            "index": 0
          }
        ]
      ]
    },
    "Simple Memory": {
      "ai_memory": [
        [
          {
            "node": "AI Agent",
            "type": "ai_memory",
            "index": 0
          }
        ]
      ]
    },
    "Calculator": {
      "ai_tool": [
        [
          {
            "node": "AI Agent",
            "type": "ai_tool",
            "index": 0
          }
        ]
      ]
    },
    "SerpAPI": {
      "ai_tool": [
        [
          {
            "node": "AI Agent",
            "type": "ai_tool",
            "index": 0
          }
        ]
      ]
    }
  },
  "active": false,
  "settings": {
    "executionOrder": "v1"
  },
  "versionId": "4ffa22fc-f47a-4e6f-b68c-937ca60330ee",
  "meta": {
    "templateCredsSetupCompleted": true,
    "instanceId": "458843d3816e5d6b17902e60d706c87928d020325a832ce0fa2baed84eae589a"
  },
  "id": "SwO8UgZ28weCLF4B",
  "tags": []
}
