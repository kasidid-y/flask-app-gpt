# flask-app-gpt (sentiment) api

## Template openai connect model
```python
import openai

# Set your OpenAI API key
openai.api_key = "your-openai-api-key"

# Define the text you want to analyze or interact with
text = """
โจนาธาน แฮ็กเกอร์ตี้ ลงป้องกันตำแหน่งแชมป์โลก ONE มวยไทย รุ่นแบนตัมเวต โดยเจอกับผู้ท้าชิงชาวไทยอย่าง ซุปเปอร์เล็ก เกียรติ หมู่ 9

อย่างไรก็ตาม เข็มขัดแชมป์โลกของ แฮ็กเกอร์ตี้ ต้องกระเด็นหลุดหลังเกมการชกผ่านไปเพียง 49 วินาที เมื่อเจ้าตัวโดนศอกเข้าตรงขมับลงไปนอนกับพื้นแล้วลุกไม่ขึ้นจนถูกจับแพ้ไป
"""

# Make a request to the OpenAI GPT-3.5 API
response = openai.ChatCompletion.create(
    model="gpt-3.5-turbo-0125",
    messages=[
        {"role": "system", "content": "Analyze the following news article and tell me it's category"},
        {"role": "user", "content": text}
    ]
)

# Extract the response text
response_text = response['choices'][0]['message']['content'].strip()

print("Response from GPT-3.5:", response_text)
```
