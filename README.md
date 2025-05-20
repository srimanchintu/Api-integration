
def classify_with_openai(url):
    import openai
    openai.api_key = "your-api-key"

    response = openai.ChatCompletion.create(
        model="gpt-4",
        messages=[
            {"role": "system", "content": "Classify this website as work, social, entertainment, or unknown."},
            {"role": "user", "content": f"The user visited {url}"}
        ]
    )
    return response.choices[0].message.content.strip()
