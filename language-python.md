# Sample Python application with Looker SDK integration
import looker_sdk
from typing import Dict, List, Optional
import json
import os

class LookerManager:
    def __init__(self, base_url: str, client_id: str, client_secret: str):
        """Initialize Looker SDK connection"""
        self.sdk = looker_sdk.init40(
            config_settings={
                'base_url': base_url,
                'client_id': client_id,
                'client_secret': client_secret
            }
        )
    
    def get_dashboards(self) -> List[Dict]:
        """Fetch all dashboards from Looker"""
        try:
            dashboards = self.sdk.all_dashboards()
            return [
                {
                    'id': dash.id,
                    'title': dash.title,
                    'description': dash.description
                }
                for dash in dashboards
            ]
        except Exception as e:
            print(f"Error fetching dashboards: {e}")
            return []
    
    def run_query(self, query_id: str) -> Dict:
        """Execute a query and return results"""
        try:
            result = self.sdk.run_query(
                query_id=query_id,
                result_format='json'
            )
            return json.loads(result)
        except Exception as e:
            print(f"Error running query: {e}")
            return {}

def main():
    # Initialize Looker connection
    looker = LookerManager(
        base_url=os.getenv('LOOKER_BASE_URL'),
        client_id=os.getenv('LOOKER_CLIENT_ID'),
        client_secret=os.getenv('LOOKER_CLIENT_SECRET')
    )
    
    # Get dashboards
    dashboards = looker.get_dashboards()
    print(f"Found {len(dashboards)} dashboards")
    
    for dashboard in dashboards[:5]:  # Show first 5
        print(f"- {dashboard['title']}")

if __name__ == "__main__":
    main()<