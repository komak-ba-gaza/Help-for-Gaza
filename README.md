import { useRouter } from 'next/router';

export default function LanguageSwitcher() {
  const router = useRouter();
  const { locale, locales, asPath } = router;

  return (
    <div className="flex space-x-4 justify-end p-4 bg-green-50">
      {locales?.map((loc) => (
        <button
          key={loc}
          disabled={loc === locale}
          onClick={() => router.push(asPath, asPath, { locale: loc })}
          className={`px-3 py-1 rounded ${loc === locale ? 'bg-green-700 text-white' : 'bg-gray-200'}`}
        >
          {loc === 'fa' ? 'فارسی' : 'English'}
        </button>
      ))}
    </div>
  );
}
