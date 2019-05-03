# Intent

代码
 protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Button btn = (Button)findViewById(R.id.button);//获取按钮
        btn.setOnClickListener(new View.OnClickListener() {       
            @Override
            public void onClick(View v) {

                EditText et = (EditText)findViewById(R.id.editText);
                String cn = et.getText().toString();
                

                Intent intent = new Intent();
                intent.setAction("android.intent.action.VIEW");

                //  intent.setClassName("com.android.browser","com.android.browser.BrowserActivity");
                //  intent.setClassName("com.example.mybrowser","com.example.mybrowser.MainActivity");
                Bundle bundle = new Bundle();
                bundle.putString("address",cn);
                intent.putExtras(bundle);

                Intent chooser = Intent.createChooser(intent, "请选择以下应用打开");
                if (intent.resolveActivity(getPackageManager()) != null) {
                    startActivity(intent);
                }


            }
        });

    }
