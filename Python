import streamlit as st
import google.generativeai as genai

# --- إعدادات الصفحة الفنية (Google AI Style) ---
st.set_page_config(page_title="EcomMind AI | المحرك الذكي", layout="wide", initial_sidebar_state="collapsed")

# --- CSS لتصميم الواجهة المبهره (Dark Google Theme) ---
st.markdown("""
    <style>
    .main { background-color: #0b0e14; color: #e8eaed; }
    .stApp { background-color: #0b0e14; }
    h1 { font-family: 'Plus Jakarta Sans', sans-serif; font-weight: 800; background: linear-gradient(90deg, #4285f4, #9b72cb, #d96570); -webkit-background-clip: text; -webkit-text-fill-color: transparent; font-size: 3.5rem !important; }
    .glass-card { background: rgba(255, 255, 255, 0.03); border: 1px solid rgba(255, 255, 255, 0.1); border-radius: 20px; padding: 25px; margin-bottom: 20px; }
    .stButton>button { width: 100%; background: linear-gradient(90deg, #4285f4, #1a73e8); border: none; color: white; padding: 15px; border-radius: 12px; font-weight: bold; transition: 0.3s; }
    .stButton>button:hover { transform: translateY(-3px); box-shadow: 0 10px 20px rgba(66, 133, 244, 0.4); }
    input { background-color: #1a1d23 !important; border-radius: 10px !important; color: white !important; }
    </style>
    """, unsafe_allow_html=True)

# --- منطق النظام الذكي ---
def generate_ecom_content(api_key, product_name):
    try:
        genai.configure(api_key=api_key)
        model = genai.GenerativeModel('gemini-1.5-flash')
        prompt = f"أنت خبير تسويق عالمي. اكتب وصفاً بيعياً مذهلاً لمنتج: {product_name} يتضمن: 1. وصف AIDA، 2. كلمات مفتاحية SEO، 3. فكرة فيديو تيك توك إبداعية."
        response = model.generate_content(prompt)
        return response.text
    except:
        return "يرجى التأكد من مفتاح الـ API الخاص بك."

# --- واجهة المستخدم (UI) ---
st.markdown("<div style='text-align: center; padding-top: 50px;'>", unsafe_allow_html=True)
st.title("EcomMind AI")
st.markdown("<p style='color: #9aa0a6; font-size: 1.2rem;'>مستقبل التجارة الإلكترونية بين يديك</p>", unsafe_allow_html=True)
st.markdown("</div>", unsafe_allow_html=True)

# نافذة إدخال البيانات
with st.container():
    col1, col2, col3 = st.columns([1, 2, 1])
    with col2:
        st.markdown("<div class='glass-card'>", unsafe_allow_html=True)
        product = st.text_input("📦 ما هو المنتج الذي تريد تسويقه؟", placeholder="مثلاً: قلاية هوائية ذكية")
        api_key_input = st.text_input("🔑 أدخل رمز الوصول الخاص بك (API Key)", type="password")
        
        if st.button("توليد الإستراتيجية الذكية ✨"):
            if product and api_key_input:
                result = generate_ecom_content(api_key_input, product)
                st.markdown("### 📝 النتائج:")
                st.write(result)
            else:
                st.error("يرجى إدخال اسم المنتج ومفتاح الوصول.")
        st.markdown("</div>", unsafe_allow_html=True)

# --- نظام الدفع المتكامل (الذي طلبته) ---
st.markdown("<hr style='border-color: rgba(255,255,255,0.1)'>", unsafe_allow_html=True)
st.markdown("<h2 style='text-align: center;'>الاشتراك في النسخة الاحترافية</h2>", unsafe_allow_html=True)

c1, c2, c3 = st.columns(3)
with c2:
    st.markdown(f"""
        <div class='glass-card' style='text-align: center; border: 2px solid #4285f4;'>
            <h3 style='color: #4285f4;'>الخطة اللامحدودة</h3>
            <p style='font-size: 2rem; font-weight: bold;'>49$ <span style='font-size: 1rem;'>/ شهرياً</span></p>
            <ul style='text-align: right; font-size: 0.9rem; color: #9aa0a6;'>
                <li>✅ وصف منتجات غير محدود</li>
                <li>✅ تحليل المنافسين بالذكاء الاصطناعي</li>
                <li>✅ دعم فني 24/7</li>
            </ul>
            <div style='margin-top: 20px;'>
                <p style='font-size: 0.8rem; color: #e8eaed;'>للدفع عبر بايونير، أرسل المبلغ إلى:</p>
                <p style='background: #1a1d23; padding: 10px; border-radius: 8px; font-weight: bold; color: #4285f4;'>SADAM.ALHAJ007@GMAIL.COM</p>
                <p style='font-size: 0.8rem; color: #e8eaed; margin-top: 10px;'>أو عبر المحفظة الرقمية (USDT - TRC20):</p>
                <p style='background: #1a1d23; padding: 10px; border-radius: 8px; font-size: 0.7rem; color: #34a853; word-break: break-all;'>TKCvNEvz59717dp5QZbrwCqCzTQqjrNxCX</p>
            </div>
            <a href="mailto:SADAM.ALHAJ007@GMAIL.COM?subject=اشتراك في EcomMind AI" style='text-decoration: none;'>
                <button style='width: 100%; background: #4285f4; color: white; border: none; padding: 12px; border-radius: 8px; font-weight: bold; cursor: pointer; margin-top: 15px;'>تأكيد الدفع وإرسال الإيصال</button>
            </a>
        </div>
    """, unsafe_allow_html=True)
