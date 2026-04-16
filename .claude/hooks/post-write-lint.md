# PostToolUse Hook — Auto Lint

# This hook runs ESLint automatically after Claude writes any .ts or .html file.
# Add this to .claude/settings.json:

# {
#   "hooks": {
#     "PostToolUse": [
#       {
#         "matcher": "Write",
#         "hooks": [
#           {
#             "type": "command",
#             "command": "npm run lint --silent 2>&1 | tail -20"
#           }
#         ]
#       }
#     ]
#   }
# }
