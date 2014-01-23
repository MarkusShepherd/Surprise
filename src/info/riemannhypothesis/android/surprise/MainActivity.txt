package info.riemannhypothesis.android.surprise;

import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.webkit.WebView;

public class MainActivity extends Activity {

	private WebView webView;

	@Override
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_main);
		webView = (WebView) findViewById(R.id.webView);
		int random = (int) (Math.random() * 4);
		switch (random) {
		case 0:
			openPage1(null);
			break;
		case 1:
			openPage2(null);
			break;
		case 2:
			openPage3(null);
			break;
		default:
			openPage4(null);
			break;
		}
	}

	@Override
	public void onBackPressed() {
		if (webView.canGoBack()) {
			webView.goBack();
		} else {
			super.onBackPressed();
		}
	}

	public void openPage1(View view) {
		webView.loadUrl("http://en.m.wikipedia.org/wiki/Android_(operating_system)");
	}

	public void openPage2(View view) {
		webView.loadUrl("http://www.riemannhypothesis.info/");
	}

	public void openPage3(View view) {
		webView.loadUrl("http://developer.android.com/index.html");
	}

	public void openPage4(View view) {
		webView.loadUrl("http://stackoverflow.com/");
	}
}
